# RemoveLogContainerSet

- ea: `0x18000cba0`
- end: `0x18000cf79`
- name: `RemoveLogContainerSet`
- size: `985`
- prototype: `BOOL __stdcall(HANDLE hLog, USHORT cContainer, LPWSTR *rgwszContainerPath, BOOL fForce, LPVOID pReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000cb50`

## callees

- `0x1800018a4`
- `0x1800026c6`
- `0x18000cba0`
- `0x180014db6`
- `0x180014dce`
- `0x180014dda`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cf2d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001559f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cf2d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001559f`
- `ntdll!RtlFreeHeap` at `0x18000cc87`
- `ntdll!RtlFreeHeap` at `0x18000ccc2`
- `ntdll!RtlFreeHeap` at `0x18000ce11`
- `ntdll!RtlFreeHeap` at `0x18000ce6e`
- `ntdll!RtlFreeHeap` at `0x18000cc87`
- `ntdll!RtlFreeHeap` at `0x18000ccc2`
- `ntdll!RtlFreeHeap` at `0x18000ce11`
- `ntdll!RtlFreeHeap` at `0x18000ce6e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18000cc5c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18000cdb3`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18000cc5c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18000cdb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf18`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000cf06`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000cf06`

## pseudocode

```c
BOOL __stdcall RemoveLogContainerSet(
        HANDLE hLog,
        USHORT cContainer,
        LPWSTR *rgwszContainerPath,
        BOOL fForce,
        LPVOID pReserved)
{
  bool v5; // r13
  int v6; // r12d
  DWORD v7; // ecx
  int v8; // r14d
  unsigned __int16 v9; // si
  LPWSTR v10; // rdi
  BOOLEAN v11; // al
  PVOID ProcessHeap; // rcx
  __int64 v13; // rbx
  size_t v14; // r14
  _WORD *v15; // rax
  _WORD *v16; // rdi
  unsigned __int16 v17; // r15
  DWORD LastError; // esi
  int v19; // r13d
  LPWSTR v20; // r14
  unsigned int v21; // ecx
  __int64 v22; // r8
  __int64 v23; // rax
  BOOL v24; // ebx
  __int64 v26; // [rsp+0h] [rbp-B8h] BYREF
  unsigned __int16 v27; // [rsp+40h] [rbp-78h]
  DWORD v28; // [rsp+44h] [rbp-74h]
  int v29; // [rsp+48h] [rbp-70h]
  DWORD nInBufferSize; // [rsp+4Ch] [rbp-6Ch]
  unsigned __int64 v31; // [rsp+50h] [rbp-68h]
  __int64 *v32; // [rsp+58h] [rbp-60h]
  void *v33; // [rsp+60h] [rbp-58h]
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-50h] BYREF
  DWORD BytesReturned; // [rsp+C8h] [rbp+10h] BYREF
  LPWSTR *v37; // [rsp+D0h] [rbp+18h]

  v37 = rgwszContainerPath;
  v32 = &v26;
  v5 = fForce;
  v6 = cContainer;
  BytesReturned = 0;
  if ( !cContainer )
  {
LABEL_38:
    v7 = 87;
    goto LABEL_39;
  }
  if ( rgwszContainerPath )
  {
    v8 = 0;
    v9 = 0;
    while ( 1 )
    {
      v10 = rgwszContainerPath[v9];
      if ( !v10 || !*v10 )
        goto LABEL_38;
      if ( !wcsncmp_0(v10, L"%BLF%\\", 6u) || !wcsncmp_0(v10, L"%BLF%:", 6u) )
      {
        v13 = -1;
        do
          ++v13;
        while ( v10[v13] );
      }
      else
      {
        NtName = 0;
        v11 = RtlDosPathNameToRelativeNtPathName_U(v10, &NtName, 0, 0);
        ProcessHeap = NtCurrentPeb()->ProcessHeap;
        if ( !v11 )
        {
          RtlFreeHeap(ProcessHeap, 0, NtName.Buffer);
          v7 = 3;
          goto LABEL_39;
        }
        LODWORD(v13) = NtName.Length >> 1;
        RtlFreeHeap(ProcessHeap, 0, NtName.Buffer);
      }
      v8 += 2 * v13 + 2;
      if ( ++v9 >= (unsigned __int16)v6 )
      {
        nInBufferSize = v8 + 2 * (v6 + 9);
        v14 = nInBufferSize;
        v15 = operator new[](nInBufferSize, (const struct std::nothrow_t *)&std::nothrow);
        v16 = v15;
        v17 = 0;
        if ( !v15 )
        {
          v7 = 8;
          goto LABEL_39;
        }
        LastError = 0;
        v28 = 0;
        v33 = v15;
        memset_0(v15, 0, v14);
        v16[4] = v6;
        *(_QWORD *)v16 = 0;
        *((_BYTE *)v16 + 10) = v5;
        v31 = (v14 - 16) >> 1;
        v19 = 0;
        while ( 1 )
        {
          v27 = v17;
          if ( v17 >= (unsigned __int16)v6 )
            break;
          v20 = v37[v17];
          if ( !wcsncmp_0(v20, L"%BLF%\\", 6u) || !wcsncmp_0(v20, L"%BLF%:", 6u) )
          {
            v22 = -1;
            do
              ++v22;
            while ( v20[v22] );
            memcpy_0(&v16[v19 + 8], v20, 2 * v22 + 2);
            v23 = -1;
            do
              ++v23;
            while ( v20[v23] );
            LODWORD(v13) = v23 + v13;
            v29 = v13;
          }
          else
          {
            NtName = 0;
            if ( !RtlDosPathNameToRelativeNtPathName_U(v20, &NtName, 0, 0) )
            {
              SetLastError(3u);
              local_unwind_0(v32, &loc_18000CF63);
            }
            v21 = NtName.Length >> 1;
            LODWORD(v13) = v21;
            v29 = v21;
            if ( (int)v31 - v19 < v21 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
              SetLastError(0x54Fu);
              local_unwind_0(v32, &loc_18000CF63);
            }
            memcpy_0(&v16[v19 + 8], NtName.Buffer, 2LL * v21);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
          }
          v19 += v13 + 1;
          ++v17;
        }
        v24 = DeviceIoControl(hLog, 0x8007A80C, v16, nInBufferSize, 0, 0, &BytesReturned, (LPOVERLAPPED)pReserved);
        if ( !v24 )
        {
          LastError = GetLastError();
          v28 = LastError;
        }
        operator delete[](v16);
        if ( LastError )
        {
          SetLastError(LastError);
          return 0;
        }
        return v24;
      }
      rgwszContainerPath = v37;
    }
  }
  v7 = 122;
LABEL_39:
  SetLastError(v7);
  return 0;
}

```

## disassembly

```asm
0x18000cba0  mov     rax, rsp
0x18000cba3  mov     [rax+18h], r8
0x18000cba7  mov     [rax+8], rcx
0x18000cbab  push    rbx
0x18000cbac  push    rsi
0x18000cbad  push    rdi
0x18000cbae  push    r12
0x18000cbb0  push    r13
0x18000cbb2  push    r14
0x18000cbb4  push    r15
0x18000cbb6  sub     rsp, 80h
0x18000cbbd  mov     [rsp+0B8h+var_60], rsp
0x18000cbc2  mov     r13d, r9d
0x18000cbc5  movzx   r12d, dx
0x18000cbc9  xor     ecx, ecx
0x18000cbcb  mov     [rax+10h], ecx
0x18000cbce  cmp     cx, r12w
0x18000cbd2  jz      loc_18000CF52
0x18000cbd8  test    r8, r8
0x18000cbdb  jnz     short loc_18000CBE6
0x18000cbdd  lea     ecx, [r8+7Ah]
0x18000cbe1  jmp     loc_18000CF57
0x18000cbe6  mov     ebx, ecx
0x18000cbe8  mov     r14d, ecx
0x18000cbeb  mov     esi, ecx
0x18000cbed  cmp     cx, r12w
0x18000cbf1  jnb     loc_18000CCD8
0x18000cbf7  mov     r15d, 6
0x18000cbfd  movzx   eax, si
0x18000cc00  mov     rdi, [r8+rax*8]
0x18000cc04  test    rdi, rdi
0x18000cc07  jz      loc_18000CF52
0x18000cc0d  cmp     cx, [rdi]
0x18000cc10  jz      loc_18000CF52
0x18000cc16  mov     r8d, r15d; MaxCount
0x18000cc19  lea     rdx, aBlf; "%BLF%\\"
0x18000cc20  mov     rcx, rdi; String1
0x18000cc23  call    wcsncmp_0
0x18000cc28  xor     ecx, ecx
0x18000cc2a  test    eax, eax
0x18000cc2c  jz      short loc_18000CC97
0x18000cc2e  mov     r8d, r15d; MaxCount
0x18000cc31  lea     rdx, aBlf_0; "%BLF%:"
0x18000cc38  mov     rcx, rdi; String1
0x18000cc3b  call    wcsncmp_0
0x18000cc40  xor     ecx, ecx
0x18000cc42  test    eax, eax
0x18000cc44  jz      short loc_18000CC97
0x18000cc46  xorps   xmm0, xmm0
0x18000cc49  movups  xmmword ptr [rsp+0B8h+NtName.Length], xmm0
0x18000cc4e  xor     r9d, r9d; RelativeName
0x18000cc51  xor     r8d, r8d; PartName
0x18000cc54  lea     rdx, [rsp+0B8h+NtName]; NtName
0x18000cc59  mov     rcx, rdi; DosName
0x18000cc5c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18000cc63  nop     dword ptr [rax+rax+00h]
0x18000cc68  mov     rcx, gs:60h
0x18000cc71  xor     edx, edx; Flags
0x18000cc73  mov     r8, [rsp+0B8h+NtName.Buffer]; P
0x18000cc78  mov     rcx, [rcx+30h]; HeapHandle
0x18000cc7c  test    al, al
0x18000cc7e  jz      short loc_18000CCC2
0x18000cc80  movzx   ebx, [rsp+0B8h+NtName.Length]
0x18000cc85  shr     ebx, 1
0x18000cc87  call    cs:__imp_RtlFreeHeap
0x18000cc8e  nop     dword ptr [rax+rax+00h]
0x18000cc93  xor     ecx, ecx
0x18000cc95  jmp     short loc_18000CCA4
0x18000cc97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cc9b  inc     rbx
0x18000cc9e  cmp     [rdi+rbx*2], cx
0x18000cca2  jnz     short loc_18000CC9B
0x18000cca4  lea     r14d, [r14+rbx*2]
0x18000cca8  add     r14d, 2
0x18000ccac  inc     si
0x18000ccaf  cmp     si, r12w
0x18000ccb3  jnb     short loc_18000CCD8
0x18000ccb5  mov     r8, [rsp+0B8h+arg_10]
0x18000ccbd  jmp     loc_18000CBFD
0x18000ccc2  call    cs:__imp_RtlFreeHeap
0x18000ccc9  nop     dword ptr [rax+rax+00h]
0x18000ccce  mov     ecx, 3
0x18000ccd3  jmp     loc_18000CF57
0x18000ccd8  lea     eax, [r12+9]
0x18000ccdd  lea     eax, [r14+rax*2]
0x18000cce1  mov     [rsp+0B8h+nInBufferSize], eax
0x18000cce5  mov     r14d, eax
0x18000cce8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ccef  mov     ecx, eax; unsigned __int64
0x18000ccf1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ccf6  mov     rdi, rax
0x18000ccf9  xor     r15d, r15d
0x18000ccfc  test    rax, rax
0x18000ccff  jnz     short loc_18000CD09
0x18000cd01  lea     ecx, [rax+8]
0x18000cd04  jmp     loc_18000CF57
0x18000cd09  mov     esi, r15d
0x18000cd0c  mov     [rsp+0B8h+var_74], r15d
0x18000cd11  mov     [rsp+0B8h+var_58], rdi
0x18000cd16  mov     r8, r14; Size
0x18000cd19  xor     edx, edx; Val
0x18000cd1b  mov     rcx, rdi; void *
0x18000cd1e  call    memset_0
0x18000cd23  nop
0x18000cd24  mov     [rdi+8], r12w
0x18000cd29  mov     [rdi], r15
0x18000cd2c  mov     [rdi+0Ah], r13b
0x18000cd30  lea     rax, [r14-10h]
0x18000cd34  shr     rax, 1
0x18000cd37  mov     [rsp+0B8h+var_68], rax
0x18000cd3c  xor     ecx, ecx
0x18000cd3e  mov     r13d, ecx
0x18000cd41  mov     [rsp+0B8h+var_78], r15w
0x18000cd47  cmp     r15w, r12w
0x18000cd4b  jnb     loc_18000CECA
0x18000cd51  movzx   eax, r15w
0x18000cd55  mov     rcx, [rsp+0B8h+arg_10]
0x18000cd5d  mov     r14, [rcx+rax*8]
0x18000cd61  mov     r8d, 6; MaxCount
0x18000cd67  lea     rdx, aBlf; "%BLF%\\"
0x18000cd6e  mov     rcx, r14; String1
0x18000cd71  call    wcsncmp_0
0x18000cd76  xor     ecx, ecx
0x18000cd78  test    eax, eax
0x18000cd7a  jz      loc_18000CE7C
0x18000cd80  lea     r8d, [rcx+6]; MaxCount
0x18000cd84  lea     rdx, aBlf_0; "%BLF%:"
0x18000cd8b  mov     rcx, r14; String1
0x18000cd8e  call    wcsncmp_0
0x18000cd93  xor     ecx, ecx
0x18000cd95  test    eax, eax
0x18000cd97  jz      loc_18000CE7C
0x18000cd9d  xorps   xmm0, xmm0
0x18000cda0  movups  xmmword ptr [rsp+0B8h+NtName.Length], xmm0
0x18000cda5  xor     r9d, r9d; RelativeName
0x18000cda8  xor     r8d, r8d; PartName
0x18000cdab  lea     rdx, [rsp+0B8h+NtName]; NtName
0x18000cdb0  mov     rcx, r14; DosName
0x18000cdb3  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18000cdba  nop     dword ptr [rax+rax+00h]
0x18000cdbf  test    al, al
0x18000cdc1  jnz     short loc_18000CDE5
0x18000cdc3  mov     ecx, 3; dwErrCode
0x18000cdc8  call    cs:__imp_SetLastError
0x18000cdcf  nop     dword ptr [rax+rax+00h]
0x18000cdd4  lea     rdx, loc_18000CF63
0x18000cddb  mov     rcx, [rsp+0B8h+var_60]
0x18000cde0  call    _local_unwind_0
0x18000cde5  movzx   ecx, [rsp+0B8h+NtName.Length]
0x18000cdea  shr     ecx, 1
0x18000cdec  mov     ebx, ecx
0x18000cdee  mov     [rsp+0B8h+var_70], ecx
0x18000cdf2  mov     eax, dword ptr [rsp+0B8h+var_68]
0x18000cdf6  sub     eax, r13d
0x18000cdf9  cmp     eax, ecx
0x18000cdfb  jnb     short loc_18000CE3F
0x18000cdfd  mov     rcx, gs:60h
0x18000ce06  mov     r8, [rsp+0B8h+NtName.Buffer]; P
0x18000ce0b  xor     edx, edx; Flags
0x18000ce0d  mov     rcx, [rcx+30h]; HeapHandle
0x18000ce11  call    cs:__imp_RtlFreeHeap
0x18000ce18  nop     dword ptr [rax+rax+00h]
0x18000ce1d  mov     ecx, 54Fh; dwErrCode
0x18000ce22  call    cs:__imp_SetLastError
0x18000ce29  nop     dword ptr [rax+rax+00h]
0x18000ce2e  lea     rdx, loc_18000CF63
0x18000ce35  mov     rcx, [rsp+0B8h+var_60]
0x18000ce3a  call    _local_unwind_0
0x18000ce3f  mov     r8d, ecx
0x18000ce42  add     r8, r8; Size
0x18000ce45  mov     eax, r13d
0x18000ce48  add     rax, 8
0x18000ce4c  lea     rcx, [rdi+rax*2]; void *
0x18000ce50  mov     rdx, [rsp+0B8h+NtName.Buffer]; Src
0x18000ce55  call    memcpy_0
0x18000ce5a  mov     rcx, gs:60h
0x18000ce63  mov     r8, [rsp+0B8h+NtName.Buffer]; P
0x18000ce68  xor     edx, edx; Flags
0x18000ce6a  mov     rcx, [rcx+30h]; HeapHandle
0x18000ce6e  call    cs:__imp_RtlFreeHeap
0x18000ce75  nop     dword ptr [rax+rax+00h]
0x18000ce7a  jmp     short loc_18000CEBB
0x18000ce7c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ce80  inc     r8
0x18000ce83  cmp     [r14+r8*2], cx
0x18000ce88  jnz     short loc_18000CE80
0x18000ce8a  lea     r8, ds:2[r8*2]; Size
0x18000ce92  mov     eax, r13d
0x18000ce95  add     rax, 8
0x18000ce99  lea     rcx, [rdi+rax*2]; void *
0x18000ce9d  mov     rdx, r14; Src
0x18000cea0  call    memcpy_0
0x18000cea5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cea9  xor     ecx, ecx
0x18000ceab  inc     rax
0x18000ceae  cmp     [r14+rax*2], cx
0x18000ceb3  jnz     short loc_18000CEAB
0x18000ceb5  add     ebx, eax
0x18000ceb7  mov     [rsp+0B8h+var_70], ebx
0x18000cebb  inc     r13d
0x18000cebe  add     r13d, ebx
0x18000cec1  inc     r15w
0x18000cec5  jmp     loc_18000CD41
0x18000ceca  mov     rax, [rsp+0B8h+pReserved]
0x18000ced2  mov     [rsp+0B8h+lpOverlapped], rax; lpOverlapped
0x18000ced7  lea     rax, [rsp+0B8h+BytesReturned]
0x18000cedf  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x18000cee4  xor     r14d, r14d
0x18000cee7  mov     [rsp+0B8h+nOutBufferSize], r14d; nOutBufferSize
0x18000ceec  mov     [rsp+0B8h+lpOutBuffer], r14; lpOutBuffer
0x18000cef1  mov     r9d, [rsp+0B8h+nInBufferSize]; nInBufferSize
0x18000cef6  mov     r8, rdi; lpInBuffer
0x18000cef9  mov     edx, 8007A80Ch; dwIoControlCode
0x18000cefe  mov     rcx, [rsp+0B8h+hDevice]; hDevice
0x18000cf06  call    cs:__imp_DeviceIoControl
0x18000cf0d  nop     dword ptr [rax+rax+00h]
0x18000cf12  mov     ebx, eax
0x18000cf14  test    eax, eax
0x18000cf16  jnz     short loc_18000CF2A
0x18000cf18  call    cs:__imp_GetLastError
0x18000cf1f  nop     dword ptr [rax+rax+00h]
0x18000cf24  mov     esi, eax
0x18000cf26  mov     [rsp+0B8h+var_74], eax
0x18000cf2a  mov     rcx, rdi
0x18000cf2d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000cf34  nop     dword ptr [rax+rax+00h]
0x18000cf39  test    esi, esi
0x18000cf3b  jz      short loc_18000CF4E
0x18000cf3d  mov     ecx, esi; dwErrCode
0x18000cf3f  call    cs:__imp_SetLastError
0x18000cf46  nop     dword ptr [rax+rax+00h]
0x18000cf4b  mov     ebx, r14d
0x18000cf4e  mov     eax, ebx
0x18000cf50  jmp     short loc_18000CF65
0x18000cf52  mov     ecx, 57h ; 'W'; dwErrCode
0x18000cf57  call    cs:__imp_SetLastError
0x18000cf5e  nop     dword ptr [rax+rax+00h]
0x18000cf63  xor     eax, eax
0x18000cf65  add     rsp, 80h
0x18000cf6c  pop     r15
0x18000cf6e  pop     r14
0x18000cf70  pop     r13
0x18000cf72  pop     r12
0x18000cf74  pop     rdi
0x18000cf75  pop     rsi
0x18000cf76  pop     rbx
0x18000cf77  retn
0x18001558d  push    rbp
0x18001558f  sub     rsp, 40h
0x180015593  mov     rbp, rdx
0x180015596  mov     rcx, [rbp+60h]
0x18001559a  test    rcx, rcx
0x18001559d  jz      short loc_1800155AC
0x18001559f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800155a6  nop     dword ptr [rax+rax+00h]
0x1800155ab  nop
0x1800155ac  mov     ecx, [rbp+44h]; dwErrCode
0x1800155af  test    ecx, ecx
0x1800155b1  jz      short loc_1800155C0
0x1800155b3  call    cs:__imp_SetLastError
0x1800155ba  nop     dword ptr [rax+rax+00h]
0x1800155bf  nop
0x1800155c0  add     rsp, 40h
0x1800155c4  pop     rbp
0x1800155c5  retn
```
