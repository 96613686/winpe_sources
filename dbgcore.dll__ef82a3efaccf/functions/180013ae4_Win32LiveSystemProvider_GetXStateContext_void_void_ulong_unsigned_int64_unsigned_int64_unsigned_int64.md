# Win32LiveSystemProvider::GetXStateContext(void *,void *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180013ae4`
- end: `0x180013c3c`
- name: `?GetXStateContext@Win32LiveSystemProvider@@AEAAJPEAX0KPEA_K11@Z`
- size: `344`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *this, void *, void *, unsigned int, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013790`

## callees

- `0x180003424`
- `0x180013ae4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013b97`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::GetXStateContext(
        Win32LiveSystemProvider *this,
        void *a2,
        void *a3,
        unsigned int a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  size_t v8; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rcx
  unsigned int (__fastcall *v15)(__int64, __int64, void **, unsigned __int64 **); // rax
  signed int LastError; // eax
  unsigned int v17; // ebx
  size_t v18; // r8
  _QWORD *v19; // rbx
  unsigned __int64 v20; // rcx
  void *Src; // [rsp+30h] [rbp-38h] BYREF

  v8 = a4;
  if ( *(&g_Kernel32CallsMdwd + 1) )
  {
    if ( *((_QWORD *)this + 93) )
    {
      if ( *((_QWORD *)this + 94) )
      {
        v11 = *((_QWORD *)this + 6);
        if ( v11 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, a4);
          v13 = v12;
          if ( !v12 )
            return (unsigned int)-2147024882;
          v14 = v12;
          Src = 0;
          v15 = (unsigned int (__fastcall *)(__int64, __int64, void **, unsigned __int64 **))*((_QWORD *)this + 94);
          LODWORD(a7) = v8;
          if ( v15(v14, 1048671, &Src, &a7) )
          {
            if ( *(&g_Kernel32CallsMdwd + 1) )
            {
              if ( (unsigned int)(*(&g_Kernel32CallsMdwd + 1))(a2, Src) )
              {
                v18 = v8;
                v19 = Src;
                memcpy_0(a3, Src, v18);
                *a5 = v19[31];
                v20 = v19[19];
                v17 = 0;
                *a6 = v20;
LABEL_15:
                (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v13);
                return v17;
              }
            }
            else
            {
              SetLastError(0x32u);
            }
          }
          if ( GetLastError() )
          {
            LastError = GetLastError();
            v17 = LastError;
            if ( LastError > 0 )
              v17 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v17 = -2147467259;
          }
          goto LABEL_15;
        }
      }
    }
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180013ae4  push    rbx
0x180013ae6  push    rbp
0x180013ae7  push    rsi
0x180013ae8  push    rdi
0x180013ae9  push    r14
0x180013aeb  sub     rsp, 40h
0x180013aef  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180013af6  mov     r14, r8
0x180013af9  mov     ebx, r9d
0x180013afc  mov     rbp, rdx
0x180013aff  mov     rdi, rcx
0x180013b02  test    rax, rax
0x180013b05  jz      loc_180013C2C
0x180013b0b  cmp     qword ptr [rcx+2E8h], 0
0x180013b13  jz      loc_180013C2C
0x180013b19  cmp     qword ptr [rcx+2F0h], 0
0x180013b21  jz      loc_180013C2C
0x180013b27  mov     rcx, [rcx+30h]
0x180013b2b  test    rcx, rcx
0x180013b2e  jz      loc_180013C2C
0x180013b34  mov     rax, [rcx]
0x180013b37  mov     edx, ebx
0x180013b39  mov     rax, [rax+8]
0x180013b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b42  mov     rsi, rax
0x180013b45  test    rax, rax
0x180013b48  jz      loc_180013C23
0x180013b4e  mov     rcx, rax
0x180013b51  mov     [rsp+68h+Src], 0
0x180013b5a  mov     rax, [rdi+2F0h]
0x180013b61  lea     r9, [rsp+68h+arg_30]
0x180013b69  lea     r8, [rsp+68h+Src]
0x180013b6e  mov     dword ptr [rsp+68h+arg_30], ebx
0x180013b75  mov     edx, 10005Fh
0x180013b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b7f  test    eax, eax
0x180013b81  jz      short loc_180013B9D
0x180013b83  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180013b8a  mov     rdx, [rsp+68h+Src]
0x180013b8f  test    rax, rax
0x180013b92  jnz     short loc_180013BBE
0x180013b94  lea     ecx, [rax+32h]; dwErrCode
0x180013b97  call    cs:__imp_SetLastError
0x180013b9d  call    cs:__imp_GetLastError
0x180013ba3  test    eax, eax
0x180013ba5  jz      short loc_180013C09
0x180013ba7  call    cs:__imp_GetLastError
0x180013bad  mov     ebx, eax
0x180013baf  test    eax, eax
0x180013bb1  jle     short loc_180013C0E
0x180013bb3  movzx   ebx, ax
0x180013bb6  or      ebx, 80070000h
0x180013bbc  jmp     short loc_180013C0E
0x180013bbe  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180013bc5  mov     rcx, rbp
0x180013bc8  call    rax
0x180013bca  test    eax, eax
0x180013bcc  jz      short loc_180013B9D
0x180013bce  mov     r8, rbx; Size
0x180013bd1  mov     rcx, r14; void *
0x180013bd4  mov     rbx, [rsp+68h+Src]
0x180013bd9  mov     rdx, rbx; Src
0x180013bdc  call    memcpy_0
0x180013be1  mov     rcx, [rbx+0F8h]
0x180013be8  mov     rax, [rsp+68h+arg_20]
0x180013bf0  mov     [rax], rcx
0x180013bf3  mov     rcx, [rbx+98h]
0x180013bfa  xor     ebx, ebx
0x180013bfc  mov     rax, [rsp+68h+arg_28]
0x180013c04  mov     [rax], rcx
0x180013c07  jmp     short loc_180013C0E
0x180013c09  mov     ebx, 80004005h
0x180013c0e  mov     rcx, [rdi+30h]
0x180013c12  mov     rdx, rsi
0x180013c15  mov     rax, [rcx]
0x180013c18  mov     rax, [rax+18h]
0x180013c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c21  jmp     short loc_180013C28
0x180013c23  mov     ebx, 8007000Eh
0x180013c28  mov     eax, ebx
0x180013c2a  jmp     short loc_180013C31
0x180013c2c  mov     eax, 80004001h
0x180013c31  add     rsp, 40h
0x180013c35  pop     r14
0x180013c37  pop     rdi
0x180013c38  pop     rsi
0x180013c39  pop     rbp
0x180013c3a  pop     rbx
0x180013c3b  retn
```
