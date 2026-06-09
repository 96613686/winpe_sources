# CMFTMultiStreamTypeHandler::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800c6db0`
- end: `0x1800c6e5c`
- name: `?GetOutputCurrentType@CMFTMultiStreamTypeHandler@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `172`
- prototype: `int(CMFTMultiStreamTypeHandler *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800c6db0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6dcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6dcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6e4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6e4b`
- `MFPlat!MFCreateMediaType` at `0x1800c6e06`
- `MFPlat!MFCreateMediaType` at `0x1800c6e06`

## pseudocode

```c
__int64 __fastcall CMFTMultiStreamTypeHandler::GetOutputCurrentType(
        CMFTMultiStreamTypeHandler *this,
        unsigned int a2,
        struct IMFMediaType **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  __int64 v4; // rsi
  HRESULT v7; // ebx
  __int64 v8; // rsi

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
  v4 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  if ( (unsigned int)v4 < *((_DWORD *)this + 74) )
  {
    if ( a3 )
    {
      v8 = *(_QWORD *)(*((_QWORD *)this + 30) + 8 * v4);
      if ( v8 )
      {
        v7 = MFCreateMediaType(a3);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 256LL))(v8, *a3);
          if ( v7 < 0 )
          {
            if ( *a3 )
            {
              ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
              *a3 = 0;
            }
          }
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
  LeaveCriticalSection(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c6db0  push    rbx
0x1800c6db2  push    rbp
0x1800c6db3  push    rsi
0x1800c6db4  push    rdi
0x1800c6db5  sub     rsp, 28h
0x1800c6db9  lea     rbp, [rcx+130h]
0x1800c6dc0  mov     esi, edx
0x1800c6dc2  mov     rbx, rcx
0x1800c6dc5  mov     rdi, r8
0x1800c6dc8  mov     rcx, rbp; lpCriticalSection
0x1800c6dcb  call    cs:__imp_EnterCriticalSection
0x1800c6dd1  cmp     esi, [rbx+128h]
0x1800c6dd7  jb      short loc_1800C6DE0
0x1800c6dd9  mov     ebx, 0C00D36B3h
0x1800c6dde  jmp     short loc_1800C6E48
0x1800c6de0  test    rdi, rdi
0x1800c6de3  jnz     short loc_1800C6DEC
0x1800c6de5  mov     ebx, 80004003h
0x1800c6dea  jmp     short loc_1800C6E48
0x1800c6dec  mov     rax, [rbx+0F0h]
0x1800c6df3  mov     rsi, [rax+rsi*8]
0x1800c6df7  test    rsi, rsi
0x1800c6dfa  jnz     short loc_1800C6E03
0x1800c6dfc  mov     ebx, 0C00D6D60h
0x1800c6e01  jmp     short loc_1800C6E48
0x1800c6e03  mov     rcx, rdi; ppMFType
0x1800c6e06  call    cs:__imp_MFCreateMediaType
0x1800c6e0c  mov     ebx, eax
0x1800c6e0e  test    eax, eax
0x1800c6e10  js      short loc_1800C6E48
0x1800c6e12  mov     rax, [rsi]
0x1800c6e15  mov     rcx, rsi
0x1800c6e18  mov     rdx, [rdi]
0x1800c6e1b  mov     rax, [rax+100h]
0x1800c6e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e27  mov     ebx, eax
0x1800c6e29  test    eax, eax
0x1800c6e2b  jns     short loc_1800C6E48
0x1800c6e2d  mov     rcx, [rdi]
0x1800c6e30  test    rcx, rcx
0x1800c6e33  jz      short loc_1800C6E48
0x1800c6e35  mov     rax, [rcx]
0x1800c6e38  mov     rax, [rax+10h]
0x1800c6e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e41  mov     qword ptr [rdi], 0
0x1800c6e48  mov     rcx, rbp; lpCriticalSection
0x1800c6e4b  call    cs:__imp_LeaveCriticalSection
0x1800c6e51  mov     eax, ebx
0x1800c6e53  add     rsp, 28h
0x1800c6e57  pop     rdi
0x1800c6e58  pop     rsi
0x1800c6e59  pop     rbp
0x1800c6e5a  pop     rbx
0x1800c6e5b  retn
```
