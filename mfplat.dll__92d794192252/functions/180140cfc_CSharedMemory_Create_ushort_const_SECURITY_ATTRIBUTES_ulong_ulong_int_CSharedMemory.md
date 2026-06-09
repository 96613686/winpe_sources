# CSharedMemory::Create(ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong,int *,CSharedMemory * *)

- ea: `0x180140cfc`
- end: `0x180140e4c`
- name: `?Create@CSharedMemory@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@KKPEAHPEAPEAV1@@Z`
- size: `336`
- prototype: `static int(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, int *, struct CSharedMemory **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800cdb94`
- `0x180136ce0`

## callees

- `0x18011fff0`
- `0x180138340`
- `0x180140cfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140d9f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180140d96`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180140d96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180140e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180140e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180140e35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180140e35`

## pseudocode

```c
__int64 __fastcall CSharedMemory::Create(
        const unsigned __int16 *a1,
        struct _SECURITY_ATTRIBUTES *a2,
        __int64 a3,
        DWORD a4,
        int *a5,
        struct CSharedMemory **a6)
{
  signed int v8; // ebx
  __int64 v9; // r9
  HANDLE FileMappingW; // rbp
  signed int LastError; // eax
  _QWORD *v12; // rax

  if ( a6 )
  {
    v8 = 0;
    *a6 = 0;
    if ( a5 )
      *a5 = 0;
    if ( !a1 )
      goto LABEL_13;
    v9 = -1;
    do
      ++v9;
    while ( a1[v9] );
    v8 = _AllocStringWorker<CTCoAllocPolicy>(a1, a2, a1);
    if ( v8 >= 0 )
    {
LABEL_13:
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, a2, 0x8000004u, 0, a4, 0);
      LastError = GetLastError();
      if ( FileMappingW || (LastError > 0 ? (v8 = (unsigned __int16)LastError | 0x80070000) : (v8 = LastError), v8 >= 0) )
      {
        v12 = operator new(0x48u);
        if ( v12 )
        {
          v12[1] = FileMappingW;
          *v12 = &CSharedMemory::`vftable';
          v12[2] = 0;
          *((_DWORD *)v12 + 6) = 0;
          v12[4] = 0;
          v12[5] = 0;
          v12[6] = 0;
          *((_DWORD *)v12 + 14) = 0;
          v12[8] = 0;
          if ( a5 )
            *a5 = 1;
          *a6 = (struct CSharedMemory *)v12;
        }
        else
        {
          v8 = -2147024882;
          if ( FileMappingW )
            CloseHandle(FileMappingW);
        }
      }
    }
  }
  else
  {
    v8 = -2147467261;
  }
  CoTaskMemFree(0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180140cfc  push    rbx
0x180140cfe  push    rbp
0x180140cff  push    rsi
0x180140d00  push    rdi
0x180140d01  push    r12
0x180140d03  push    r14
0x180140d05  push    r15
0x180140d07  sub     rsp, 40h
0x180140d0b  mov     r15, [rsp+78h+arg_28]
0x180140d13  xor     r12d, r12d
0x180140d16  mov     [rsp+78h+var_48], r12
0x180140d1b  mov     esi, r9d
0x180140d1e  mov     rbp, rdx
0x180140d21  mov     edi, r12d
0x180140d24  test    r15, r15
0x180140d27  jnz     short loc_180140D33
0x180140d29  mov     ebx, 80004003h
0x180140d2e  jmp     loc_180140E32
0x180140d33  mov     r14, [rsp+78h+arg_20]
0x180140d3b  mov     ebx, r12d
0x180140d3e  mov     [r15], r12
0x180140d41  test    r14, r14
0x180140d44  jz      short loc_180140D49
0x180140d46  mov     [r14], r12d
0x180140d49  test    rcx, rcx
0x180140d4c  jz      short loc_180140D7D
0x180140d4e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180140d52  inc     r9
0x180140d55  cmp     [rcx+r9*2], r12w
0x180140d5a  jnz     short loc_180140D52
0x180140d5c  lea     rax, [rsp+78h+var_48]
0x180140d61  mov     r8, rcx
0x180140d64  mov     [rsp+78h+lpName], rax
0x180140d69  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180140d6e  mov     rdi, [rsp+78h+var_48]
0x180140d73  mov     ebx, eax
0x180140d75  test    eax, eax
0x180140d77  js      loc_180140E32
0x180140d7d  mov     [rsp+78h+lpName], rdi; lpName
0x180140d82  xor     r9d, r9d; dwMaximumSizeHigh
0x180140d85  mov     r8d, 8000004h; flProtect
0x180140d8b  mov     [rsp+78h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x180140d8f  mov     rdx, rbp; lpFileMappingAttributes
0x180140d92  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180140d96  call    cs:__imp_CreateFileMappingW
0x180140d9c  mov     rbp, rax
0x180140d9f  call    cs:__imp_GetLastError
0x180140da5  mov     esi, eax
0x180140da7  test    rbp, rbp
0x180140daa  jnz     short loc_180140DC1
0x180140dac  test    eax, eax
0x180140dae  jg      short loc_180140DB4
0x180140db0  mov     ebx, eax
0x180140db2  jmp     short loc_180140DBD
0x180140db4  movzx   ebx, si
0x180140db7  or      ebx, 80070000h
0x180140dbd  test    ebx, ebx
0x180140dbf  js      short loc_180140E32
0x180140dc1  mov     ecx, 48h ; 'H'; Size
0x180140dc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180140dcb  test    rax, rax
0x180140dce  jz      short loc_180140E1F
0x180140dd0  mov     [rax+8], rbp
0x180140dd4  lea     rcx, ??_7CSharedMemory@@6B@; const CSharedMemory::`vftable'
0x180140ddb  mov     [rax], rcx
0x180140dde  mov     [rax+10h], r12
0x180140de2  mov     [rax+18h], r12d
0x180140de6  mov     [rax+20h], rdi
0x180140dea  mov     [rax+28h], r12
0x180140dee  mov     [rax+30h], r12
0x180140df2  mov     [rax+38h], r12d
0x180140df6  mov     [rax+40h], r12
0x180140dfa  test    r14, r14
0x180140dfd  jz      short loc_180140E17
0x180140dff  test    rdi, rdi
0x180140e02  jz      short loc_180140E0F
0x180140e04  mov     ecx, r12d
0x180140e07  cmp     esi, 0B7h
0x180140e0d  jz      short loc_180140E14
0x180140e0f  mov     ecx, 1
0x180140e14  mov     [r14], ecx
0x180140e17  mov     [r15], rax
0x180140e1a  mov     rdi, r12
0x180140e1d  jmp     short loc_180140E32
0x180140e1f  mov     ebx, 8007000Eh
0x180140e24  test    rbp, rbp
0x180140e27  jz      short loc_180140E32
0x180140e29  mov     rcx, rbp; hObject
0x180140e2c  call    cs:__imp_CloseHandle
0x180140e32  mov     rcx, rdi; pv
0x180140e35  call    cs:__imp_CoTaskMemFree
0x180140e3b  mov     eax, ebx
0x180140e3d  add     rsp, 40h
0x180140e41  pop     r15
0x180140e43  pop     r14
0x180140e45  pop     r12
0x180140e47  pop     rdi
0x180140e48  pop     rsi
0x180140e49  pop     rbp
0x180140e4a  pop     rbx
0x180140e4b  retn
```
