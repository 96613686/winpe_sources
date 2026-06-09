# CMFTMultiStreamTypeHandler::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800c6a30`
- end: `0x1800c6aff`
- name: `?GetInputCurrentType@CMFTMultiStreamTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(CMFTMultiStreamTypeHandler *__hidden this, unsigned int, IMFMediaType **ppMFType)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800c6a30`
- `0x1800c7380`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6a4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6a4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6aee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6aee`
- `MFPlat!MFCreateMediaType` at `0x1800c6aa7`
- `MFPlat!MFCreateMediaType` at `0x1800c6aa7`

## pseudocode

```c
__int64 __fastcall CMFTMultiStreamTypeHandler::GetInputCurrentType(
        CMFTMultiStreamTypeHandler *this,
        unsigned int a2,
        IMFMediaType **ppMFType)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  int v7; // ebx
  __int64 v8; // rbx
  HRESULT v9; // eax
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  v11 = 0;
  v7 = CMFTMultiStreamTypeHandler::InputStreamIdToStreamIndex(this, a2, &v11);
  if ( v7 >= 0 )
  {
    if ( v11 < *((_DWORD *)this + 73) )
    {
      if ( ppMFType )
      {
        v8 = *(_QWORD *)(*((_QWORD *)this + 8) + 8LL * v11);
        if ( v8 )
        {
          v9 = MFCreateMediaType(ppMFType);
          if ( v9 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 256LL))(v8, *ppMFType);
            if ( v7 < 0 && *ppMFType )
            {
              ((void (__fastcall *)(_QWORD))(*ppMFType)->lpVtbl->Release)(*ppMFType);
              *ppMFType = 0;
            }
          }
          else
          {
            v7 = v9;
          }
        }
        else
        {
          v7 = -1072861856;
        }
      }
      else
      {
        v7 = -2147467261;
      }
    }
    else
    {
      v7 = -1072875853;
    }
  }
  LeaveCriticalSection(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c6a30  push    rbx
0x1800c6a32  push    rbp
0x1800c6a33  push    rsi
0x1800c6a34  push    rdi
0x1800c6a35  sub     rsp, 28h
0x1800c6a39  lea     rbp, [rcx+130h]
0x1800c6a40  mov     rsi, rcx
0x1800c6a43  mov     rcx, rbp; lpCriticalSection
0x1800c6a46  mov     rdi, r8
0x1800c6a49  mov     ebx, edx
0x1800c6a4b  call    cs:__imp_EnterCriticalSection
0x1800c6a51  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1800c6a56  mov     [rsp+48h+arg_0], 0
0x1800c6a5e  mov     edx, ebx; unsigned int
0x1800c6a60  mov     rcx, rsi; this
0x1800c6a63  call    ?InputStreamIdToStreamIndex@CMFTMultiStreamTypeHandler@@QEAAJKPEAK@Z; CMFTMultiStreamTypeHandler::InputStreamIdToStreamIndex(ulong,ulong *)
0x1800c6a68  mov     ebx, eax
0x1800c6a6a  test    eax, eax
0x1800c6a6c  js      short loc_1800C6AEB
0x1800c6a6e  mov     eax, [rsp+48h+arg_0]
0x1800c6a72  cmp     eax, [rsi+124h]
0x1800c6a78  jb      short loc_1800C6A81
0x1800c6a7a  mov     ebx, 0C00D36B3h
0x1800c6a7f  jmp     short loc_1800C6AEB
0x1800c6a81  test    rdi, rdi
0x1800c6a84  jnz     short loc_1800C6A8D
0x1800c6a86  mov     ebx, 80004003h
0x1800c6a8b  jmp     short loc_1800C6AEB
0x1800c6a8d  mov     rcx, rax
0x1800c6a90  mov     rax, [rsi+40h]
0x1800c6a94  mov     rbx, [rax+rcx*8]
0x1800c6a98  test    rbx, rbx
0x1800c6a9b  jnz     short loc_1800C6AA4
0x1800c6a9d  mov     ebx, 0C00D6D60h
0x1800c6aa2  jmp     short loc_1800C6AEB
0x1800c6aa4  mov     rcx, rdi; ppMFType
0x1800c6aa7  call    cs:__imp_MFCreateMediaType
0x1800c6aad  test    eax, eax
0x1800c6aaf  jns     short loc_1800C6AB5
0x1800c6ab1  mov     ebx, eax
0x1800c6ab3  jmp     short loc_1800C6AEB
0x1800c6ab5  mov     rax, [rbx]
0x1800c6ab8  mov     rcx, rbx
0x1800c6abb  mov     rdx, [rdi]
0x1800c6abe  mov     rax, [rax+100h]
0x1800c6ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6aca  mov     ebx, eax
0x1800c6acc  test    eax, eax
0x1800c6ace  jns     short loc_1800C6AEB
0x1800c6ad0  mov     rcx, [rdi]
0x1800c6ad3  test    rcx, rcx
0x1800c6ad6  jz      short loc_1800C6AEB
0x1800c6ad8  mov     rdx, [rcx]
0x1800c6adb  mov     rax, [rdx+10h]
0x1800c6adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6ae4  mov     qword ptr [rdi], 0
0x1800c6aeb  mov     rcx, rbp; lpCriticalSection
0x1800c6aee  call    cs:__imp_LeaveCriticalSection
0x1800c6af4  mov     eax, ebx
0x1800c6af6  add     rsp, 28h
0x1800c6afa  pop     rdi
0x1800c6afb  pop     rsi
0x1800c6afc  pop     rbp
0x1800c6afd  pop     rbx
0x1800c6afe  retn
```
