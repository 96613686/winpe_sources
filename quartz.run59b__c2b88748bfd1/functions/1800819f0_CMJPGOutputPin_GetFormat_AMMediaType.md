# CMJPGOutputPin::GetFormat(_AMMediaType * *)

- ea: `0x1800819f0`
- end: `0x180081ac0`
- name: `?GetFormat@CMJPGOutputPin@@UEAAJPEAPEAU_AMMediaType@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CMJPGOutputPin *__hidden this, struct _AMMediaType **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180081cc0`

## callees

- `0x180039250`
- `0x1800819f0`
- `0x180144ae0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180081aa8`
- `KERNEL32!LeaveCriticalSection` at `0x180081aa8`
- `KERNEL32!EnterCriticalSection` at `0x180081a14`
- `KERNEL32!EnterCriticalSection` at `0x180081a14`
- `ole32!CoTaskMemFree` at `0x180081a8a`
- `ole32!CoTaskMemFree` at `0x180081a8a`
- `ole32!CoTaskMemAlloc` at `0x180081a4c`
- `ole32!CoTaskMemAlloc` at `0x180081a4c`

## pseudocode

```c
__int64 __fastcall CMJPGOutputPin::GetFormat(CMJPGOutputPin *this, LPVOID *a2)
{
  CTransformOutputPin *v2; // rbp
  __int64 v4; // rsi
  unsigned int MediaType; // ebx
  struct _AMMediaType *v7; // rax

  v2 = (CMJPGOutputPin *)((char *)this - 248);
  v4 = *((_QWORD *)this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 136));
  if ( a2 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 216LL) + 48LL) )
    {
      v7 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
      *a2 = v7;
      if ( v7 )
      {
        memset_0(v7, 0, sizeof(struct _AMMediaType));
        MediaType = CTransformOutputPin::GetMediaType(v2, 0, (struct CMediaType *)*a2);
        if ( MediaType )
        {
          CoTaskMemFree(*a2);
          *a2 = 0;
        }
        else
        {
          MediaType = 0;
        }
      }
      else
      {
        MediaType = -2147024882;
      }
    }
    else
    {
      MediaType = -2147220983;
    }
  }
  else
  {
    MediaType = -2147467261;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 136));
  return MediaType;
}

```

## disassembly

```asm
0x1800819f0  push    rbx
0x1800819f2  push    rbp
0x1800819f3  push    rsi
0x1800819f4  push    rdi
0x1800819f5  sub     rsp, 28h
0x1800819f9  lea     rbp, [rcx-0F8h]
0x180081a00  mov     rbx, rcx
0x180081a03  mov     rsi, [rbp+108h]
0x180081a0a  mov     rdi, rdx
0x180081a0d  lea     rcx, [rsi+88h]; lpCriticalSection
0x180081a14  call    cs:__imp_EnterCriticalSection
0x180081a1b  nop     dword ptr [rax+rax+00h]
0x180081a20  test    rdi, rdi
0x180081a23  jnz     short loc_180081A2C
0x180081a25  mov     ebx, 80004003h
0x180081a2a  jmp     short loc_180081AA1
0x180081a2c  mov     rax, [rbx+10h]
0x180081a30  mov     rcx, [rax+0D8h]
0x180081a37  cmp     qword ptr [rcx+30h], 0
0x180081a3c  jnz     short loc_180081A45
0x180081a3e  mov     ebx, 80040209h
0x180081a43  jmp     short loc_180081AA1
0x180081a45  mov     ebx, 58h ; 'X'
0x180081a4a  mov     ecx, ebx; cb
0x180081a4c  call    cs:__imp_CoTaskMemAlloc
0x180081a53  nop     dword ptr [rax+rax+00h]
0x180081a58  mov     [rdi], rax
0x180081a5b  test    rax, rax
0x180081a5e  jnz     short loc_180081A67
0x180081a60  mov     ebx, 8007000Eh
0x180081a65  jmp     short loc_180081AA1
0x180081a67  mov     r8, rbx; Size
0x180081a6a  xor     edx, edx; Val
0x180081a6c  mov     rcx, rax; void *
0x180081a6f  call    memset_0
0x180081a74  mov     r8, [rdi]; struct CMediaType *
0x180081a77  xor     edx, edx; int
0x180081a79  mov     rcx, rbp; this
0x180081a7c  call    ?GetMediaType@CTransformOutputPin@@UEAAJHPEAVCMediaType@@@Z; CTransformOutputPin::GetMediaType(int,CMediaType *)
0x180081a81  mov     ebx, eax
0x180081a83  test    eax, eax
0x180081a85  jz      short loc_180081A9F
0x180081a87  mov     rcx, [rdi]; pv
0x180081a8a  call    cs:__imp_CoTaskMemFree
0x180081a91  nop     dword ptr [rax+rax+00h]
0x180081a96  mov     qword ptr [rdi], 0
0x180081a9d  jmp     short loc_180081AA1
0x180081a9f  xor     ebx, ebx
0x180081aa1  lea     rcx, [rsi+88h]; lpCriticalSection
0x180081aa8  call    cs:__imp_LeaveCriticalSection
0x180081aaf  nop     dword ptr [rax+rax+00h]
0x180081ab4  mov     eax, ebx
0x180081ab6  add     rsp, 28h
0x180081aba  pop     rdi
0x180081abb  pop     rsi
0x180081abc  pop     rbp
0x180081abd  pop     rbx
0x180081abe  retn
```
