# CMILCOMBaseWeakRefSource<CResourceDeleter>::InternalRelease(void)

- ea: `0x180133cf0`
- end: `0x180133e17`
- name: `?InternalRelease@?$CMILCOMBaseWeakRefSource@VCResourceDeleter@@@@IEAAKXZ`
- size: `295`
- prototype: ``
- caller_count: `36`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002acb0`
- `0x18002b16c`
- `0x18002b8cc`
- `0x18003d34c`
- `0x1800f6f0c`
- `0x180133290`
- `0x180134880`
- `0x180134900`
- `0x18013491c`
- `0x180134f50`
- `0x18013530c`
- `0x18013549c`
- `0x18013d7b8`
- `0x18015d7d4`
- `0x180170768`
- `0x18017b200`
- `0x180183d98`
- `0x18018476c`
- `0x18018a9e8`
- `0x18018b7b8`
- `0x18018d3b0`
- `0x1801ab038`
- `0x1801b8cd8`
- `0x1801bd7f0`
- `0x1801ca28c`
- `0x1801db130`
- `0x1801def5c`
- `0x18020e26c`
- `0x1802139e0`
- `0x180216934`
- `0x18021a9b0`
- `0x180227300`
- `0x1802511b0`
- `0x180259894`
- `0x18026fcb0`
- `0x18029afb0`

## callees

- `0x180133cf0`
- `0x180133e20`
- `0x180202b80`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133d3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133d3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180133d18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180133d18`

## string_xrefs

- `0x180133d62`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180133d87`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180133de0`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180133dfe`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILCOMBaseWeakRefSource<CResourceDeleter>::InternalRelease(CResource *this)
{
  __int64 v1; // rbx
  int v3; // edi
  int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 8LL))(*((_QWORD *)this + 2));
    EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
  }
  v3 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( v3 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v5);
  if ( !v3 )
  {
    if ( _InterlockedAdd((volatile signed __int32 *)this + 2, 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v5);
    (*(void (__fastcall **)(CResource *))(*(_QWORD *)this + 40LL))(this);
    v3 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
    if ( v3 < -1 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v5);
    if ( !v3 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)this + 2) < -1 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
          (const char *)0x8007029CLL,
          v5);
      CResource::Delete(this);
    }
  }
  if ( v1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180133cf0  push    rbx
0x180133cf2  push    rbp
0x180133cf3  push    rsi
0x180133cf4  push    rdi
0x180133cf5  sub     rsp, 28h
0x180133cf9  mov     rbx, [rcx+10h]
0x180133cfd  mov     rsi, rcx
0x180133d00  test    rbx, rbx
0x180133d03  jz      short loc_180133D1E
0x180133d05  mov     rax, [rbx]
0x180133d08  mov     rcx, rbx
0x180133d0b  mov     rax, [rax+8]
0x180133d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d14  lea     rcx, [rbx+10h]; lpCriticalSection
0x180133d18  call    cs:__imp_EnterCriticalSection
0x180133d1e  mov     ebp, 0FFFFFFFFh
0x180133d23  mov     edi, ebp
0x180133d25  lock xadd [rsi+8], edi
0x180133d2a  dec     edi
0x180133d2c  cmp     edi, ebp
0x180133d2e  jl      short loc_180133D5D
0x180133d30  test    edi, edi
0x180133d32  jz      short loc_180133D7B
0x180133d34  test    rbx, rbx
0x180133d37  jz      short loc_180133D52
0x180133d39  lea     rcx, [rbx+10h]; lpCriticalSection
0x180133d3d  call    cs:__imp_LeaveCriticalSection
0x180133d43  mov     rcx, [rbx]
0x180133d46  mov     rax, [rcx+10h]
0x180133d4a  mov     rcx, rbx
0x180133d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d52  mov     eax, edi
0x180133d54  add     rsp, 28h
0x180133d58  pop     rdi
0x180133d59  pop     rsi
0x180133d5a  pop     rbp
0x180133d5b  pop     rbx
0x180133d5c  retn
0x180133d5d  mov     rcx, [rsp+48h]; this
0x180133d62  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x180133d69  mov     r9d, 8007029Ch; char *
0x180133d6f  mov     edx, 26h ; '&'; void *
0x180133d74  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180133d79  jmp     short loc_180133D30
0x180133d7b  lock add dword ptr [rsi+8], 1
0x180133d80  jg      short loc_180133D9E
0x180133d82  mov     rcx, [rsp+48h]; this
0x180133d87  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x180133d8e  mov     r9d, 8007029Ch; char *
0x180133d94  mov     edx, 18h; void *
0x180133d99  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180133d9e  mov     rax, [rsi]
0x180133da1  mov     rcx, rsi
0x180133da4  mov     rax, [rax+28h]
0x180133da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133dad  mov     edi, ebp
0x180133daf  lock xadd [rsi+8], edi
0x180133db4  dec     edi
0x180133db6  cmp     edi, ebp
0x180133db8  jl      short loc_180133DDB
0x180133dba  test    edi, edi
0x180133dbc  jnz     loc_180133D34
0x180133dc2  lock xadd [rsi+8], ebp
0x180133dc7  dec     ebp
0x180133dc9  cmp     ebp, 0FFFFFFFFh
0x180133dcc  jl      short loc_180133DF9
0x180133dce  mov     rcx, rsi; this
0x180133dd1  call    ?Delete@CResource@@IEAAXXZ; CResource::Delete(void)
0x180133dd6  jmp     loc_180133D34
0x180133ddb  mov     rcx, [rsp+48h]; this
0x180133de0  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x180133de7  mov     r9d, 8007029Ch; char *
0x180133ded  mov     edx, 26h ; '&'; void *
0x180133df2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180133df7  jmp     short loc_180133DBA
0x180133df9  mov     rcx, [rsp+48h]; this
0x180133dfe  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x180133e05  mov     r9d, 8007029Ch; char *
0x180133e0b  mov     edx, 26h ; '&'; void *
0x180133e10  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180133e15  jmp     short loc_180133DCE
```
