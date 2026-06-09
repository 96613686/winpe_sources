# CLoader::ClearCacheInternal(_GUID const &,bool)

- ea: `0x18000828c`
- end: `0x1800083aa`
- name: `?ClearCacheInternal@CLoader@@AEAAJAEBU_GUID@@_N@Z`
- size: `286`
- prototype: `__int64 __fastcall(CLoader *__hidden this, const struct _GUID *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180008280`
- `0x1800094c0`

## callees

- `0x1800015d0`
- `0x18000828c`
- `0x1800089e4`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000a1e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000837d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000837d`

## pseudocode

```c
__int64 __fastcall CLoader::ClearCacheInternal(CClass **this, const struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  bool v5; // dl
  bool v6; // zf
  CClass *v7; // rdi
  int v8; // esi
  __int128 v10; // xmm0
  unsigned __int64 v11; // rdx
  int v12; // edi
  struct CClass *v13; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v14[8]; // [rsp+30h] [rbp-C8h] BYREF
  int v15; // [rsp+38h] [rbp-C0h]
  __int128 v16; // [rsp+4Ch] [rbp-ACh]

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 71);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 71));
  v6 = *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_DirectMusicAllTypes.Data1;
  v13 = 0;
  if ( !v6 || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_DirectMusicAllTypes.Data4 )
  {
    CDescriptor::CDescriptor((CDescriptor *)v14);
    v10 = (__int128)*a2;
    v15 = 2;
    v16 = v10;
    CLoader::GetClass((CLoader *)this, (struct CDescriptor *)v14, &v13, 0);
    if ( v13 )
    {
      v12 = CClass::ClearCache(v13, v11);
      if ( v12 < 0 )
      {
        CDescriptor::~CDescriptor((CDescriptor *)v14, v11);
LABEL_13:
        LeaveCriticalSection(v2);
        return (unsigned int)v12;
      }
    }
    CDescriptor::~CDescriptor((CDescriptor *)v14, v11);
LABEL_12:
    v12 = 0;
    goto LABEL_13;
  }
  v7 = this[3];
  if ( !v7 )
    goto LABEL_12;
  while ( 1 )
  {
    v8 = CClass::ClearCache(v7, v5);
    if ( v8 < 0 )
      break;
    v7 = *(CClass **)v7;
    if ( !v7 )
      goto LABEL_12;
  }
  LeaveCriticalSection(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000828c  mov     [rsp+arg_10], rbx
0x180008291  mov     [rsp+arg_18], rsi
0x180008296  push    rdi
0x180008297  sub     rsp, 0F0h
0x18000829e  mov     rax, cs:__security_cookie
0x1800082a5  xor     rax, rsp
0x1800082a8  mov     [rsp+0F8h+var_18], rax
0x1800082b0  lea     rbx, [rcx+238h]
0x1800082b7  mov     rdi, rcx
0x1800082ba  mov     rcx, rbx; lpCriticalSection
0x1800082bd  mov     rsi, rdx
0x1800082c0  call    cs:__imp_EnterCriticalSection
0x1800082c6  mov     rax, [rsi]
0x1800082c9  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data1
0x1800082d0  mov     [rsp+0F8h+var_D8], 0
0x1800082d9  jnz     short loc_18000831D
0x1800082db  mov     rax, [rsi+8]
0x1800082df  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data4
0x1800082e6  jnz     short loc_18000831D
0x1800082e8  mov     rdi, [rdi+18h]
0x1800082ec  test    rdi, rdi
0x1800082ef  jz      loc_180008378
0x1800082f5  mov     rcx, rdi; this
0x1800082f8  call    ?ClearCache@CClass@@QEAAJ_N@Z; CClass::ClearCache(bool)
0x1800082fd  mov     esi, eax
0x1800082ff  test    eax, eax
0x180008301  js      short loc_180008310
0x180008303  mov     rax, [rdi]
0x180008306  mov     rdi, rax
0x180008309  test    rax, rax
0x18000830c  jnz     short loc_1800082F5
0x18000830e  jmp     short loc_180008378
0x180008310  mov     rcx, rbx; lpCriticalSection
0x180008313  call    cs:__imp_LeaveCriticalSection
0x180008319  mov     eax, esi
0x18000831b  jmp     short loc_180008385
0x18000831d  lea     rcx, [rsp+0F8h+var_C8]; this
0x180008322  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180008327  movups  xmm0, xmmword ptr [rsi]
0x18000832a  xor     r9d, r9d; int
0x18000832d  mov     [rsp+0F8h+var_C0], 2
0x180008335  lea     r8, [rsp+0F8h+var_D8]; struct CClass **
0x18000833a  mov     rcx, rdi; this
0x18000833d  lea     rdx, [rsp+0F8h+var_C8]; struct CDescriptor *
0x180008342  movdqu  [rsp+0F8h+var_AC], xmm0
0x180008348  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x18000834d  mov     rcx, [rsp+0F8h+var_D8]; this
0x180008352  test    rcx, rcx
0x180008355  jz      short loc_18000836E
0x180008357  call    ?ClearCache@CClass@@QEAAJ_N@Z; CClass::ClearCache(bool)
0x18000835c  mov     edi, eax
0x18000835e  test    eax, eax
0x180008360  jns     short loc_18000836E
0x180008362  lea     rcx, [rsp+0F8h+var_C8]; this
0x180008367  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000836c  jmp     short loc_18000837A
0x18000836e  lea     rcx, [rsp+0F8h+var_C8]; this
0x180008373  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x180008378  xor     edi, edi
0x18000837a  mov     rcx, rbx; lpCriticalSection
0x18000837d  call    cs:__imp_LeaveCriticalSection
0x180008383  mov     eax, edi
0x180008385  mov     rcx, [rsp+0F8h+var_18]
0x18000838d  xor     rcx, rsp; StackCookie
0x180008390  call    __security_check_cookie
0x180008395  lea     r11, [rsp+0F8h+var_8]
0x18000839d  mov     rbx, [r11+20h]
0x1800083a1  mov     rsi, [r11+28h]
0x1800083a5  mov     rsp, r11
0x1800083a8  pop     rdi
0x1800083a9  retn
```
