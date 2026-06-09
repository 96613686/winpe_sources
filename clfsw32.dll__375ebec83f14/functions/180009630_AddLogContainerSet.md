# AddLogContainerSet

- ea: `0x180009630`
- end: `0x180009a0a`
- name: `AddLogContainerSet`
- size: `986`
- prototype: `BOOL __stdcall(HANDLE hLog, USHORT cContainer, PULONGLONG pcbContainer, LPWSTR *rgwszContainerPath, LPVOID pReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800095e0`

## callees

- `0x1800018a4`
- `0x1800026c6`
- `0x180009630`
- `0x180014db6`
- `0x180014dce`
- `0x180014dda`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800099d3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015297`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800099d3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015297`
- `ntdll!RtlFreeHeap` at `0x18000972c`
- `ntdll!RtlFreeHeap` at `0x180009765`
- `ntdll!RtlFreeHeap` at `0x1800098b2`
- `ntdll!RtlFreeHeap` at `0x18000990f`
- `ntdll!RtlFreeHeap` at `0x18000972c`
- `ntdll!RtlFreeHeap` at `0x180009765`
- `ntdll!RtlFreeHeap` at `0x1800098b2`
- `ntdll!RtlFreeHeap` at `0x18000990f`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180009701`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180009854`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180009701`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180009854`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800099e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800099e8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800099b0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800099b0`

## pseudocode

```c
BOOL __stdcall AddLogContainerSet(
        HANDLE hLog,
        USHORT cContainer,
        PULONGLONG pcbContainer,
        LPWSTR *rgwszContainerPath,
        LPVOID pReserved)
{
  int v6; // r15d
  DWORD v7; // ecx
  unsigned __int16 v8; // si
  int v9; // r14d
  LPWSTR v10; // rdi
  BOOLEAN v11; // al
  PVOID ProcessHeap; // rcx
  __int64 v13; // rbx
  size_t v14; // rsi
  _WORD *v15; // rax
  _WORD *v16; // rdi
  unsigned __int16 v17; // si
  int v18; // r13d
  LPWSTR v19; // r14
  unsigned int v20; // ecx
  __int64 v21; // r8
  __int64 v22; // rax
  BOOL v23; // ebx
  __int64 v25; // [rsp+0h] [rbp-B8h] BYREF
  unsigned __int16 v26; // [rsp+40h] [rbp-78h]
  int v27; // [rsp+44h] [rbp-74h]
  DWORD nInBufferSize; // [rsp+48h] [rbp-70h]
  ULONGLONG OutBuffer; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int64 v30; // [rsp+58h] [rbp-60h]
  __int64 *v31; // [rsp+60h] [rbp-58h]
  void *v32; // [rsp+68h] [rbp-50h]
  struct _UNICODE_STRING NtName; // [rsp+70h] [rbp-48h] BYREF
  DWORD BytesReturned; // [rsp+C8h] [rbp+10h] BYREF
  LPWSTR *v36; // [rsp+D8h] [rbp+20h]

  v36 = rgwszContainerPath;
  v31 = &v25;
  v6 = cContainer;
  OutBuffer = -1;
  BytesReturned = 0;
  if ( !cContainer )
  {
LABEL_39:
    v7 = 87;
    goto LABEL_40;
  }
  if ( rgwszContainerPath )
  {
    if ( pcbContainer )
      OutBuffer = *pcbContainer;
    v8 = 0;
    v9 = 0;
    while ( 1 )
    {
      v10 = rgwszContainerPath[v8];
      if ( !v10 || !*v10 )
        goto LABEL_39;
      if ( !wcsncmp_0(rgwszContainerPath[v8], L"%BLF%\\", 6u) || !wcsncmp_0(v10, L"%BLF%:", 6u) )
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
          goto LABEL_40;
        }
        LODWORD(v13) = NtName.Length >> 1;
        RtlFreeHeap(ProcessHeap, 0, NtName.Buffer);
      }
      v9 += v13 + 1;
      if ( ++v8 >= (unsigned __int16)v6 )
      {
        nInBufferSize = 2 * (v9 + v6) + 16;
        v14 = nInBufferSize;
        v15 = operator new[](nInBufferSize, (const struct std::nothrow_t *)&std::nothrow);
        v16 = v15;
        if ( !v15 )
        {
          v7 = 8;
          goto LABEL_40;
        }
        v32 = v15;
        memset_0(v15, 0, v14);
        v16[4] = v6;
        *(_QWORD *)v16 = OutBuffer;
        v30 = (v14 - 16) >> 1;
        v17 = 0;
        v26 = 0;
        v18 = 0;
        while ( v17 < (unsigned __int16)v6 )
        {
          v19 = v36[v17];
          if ( !wcsncmp_0(v19, L"%BLF%\\", 6u) || !wcsncmp_0(v19, L"%BLF%:", 6u) )
          {
            v21 = -1;
            do
              ++v21;
            while ( v19[v21] );
            memcpy_0(&v16[v18 + 8], v19, 2 * v21 + 2);
            v22 = -1;
            do
              ++v22;
            while ( v19[v22] );
            LODWORD(v13) = v22 + v13;
            v27 = v13;
          }
          else
          {
            NtName = 0;
            if ( !RtlDosPathNameToRelativeNtPathName_U(v19, &NtName, 0, 0) )
            {
              SetLastError(3u);
              local_unwind_0(v31, &loc_1800099F4);
            }
            v20 = NtName.Length >> 1;
            LODWORD(v13) = v20;
            v27 = v20;
            if ( (int)v30 - v18 < v20 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
              SetLastError(0x54Fu);
              local_unwind_0(v31, &loc_1800099F4);
            }
            memcpy_0(&v16[v18 + 8], NtName.Buffer, 2LL * v20);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
          }
          v18 += v13 + 1;
          v26 = ++v17;
        }
        v23 = DeviceIoControl(
                hLog,
                0x8007A808,
                v16,
                nInBufferSize,
                &OutBuffer,
                8u,
                &BytesReturned,
                (LPOVERLAPPED)pReserved);
        if ( v23 && pcbContainer )
          *pcbContainer = OutBuffer;
        operator delete[](v16);
        return v23;
      }
      rgwszContainerPath = v36;
    }
  }
  v7 = 122;
LABEL_40:
  SetLastError(v7);
  return 0;
}

```

## disassembly

```asm
0x180009630  mov     rax, rsp
0x180009633  mov     [rax+20h], r9
0x180009637  mov     [rax+8], rcx
0x18000963b  push    rbx
0x18000963c  push    rsi
0x18000963d  push    rdi
0x18000963e  push    r12
0x180009640  push    r13
0x180009642  push    r14
0x180009644  push    r15
0x180009646  sub     rsp, 80h
0x18000964d  mov     [rsp+0B8h+var_58], rsp
0x180009652  mov     r12, r8
0x180009655  movzx   r15d, dx
0x180009659  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFFh
0x180009661  xor     ecx, ecx
0x180009663  mov     [rax+10h], ecx
0x180009666  cmp     cx, r15w
0x18000966a  jz      loc_1800099E3
0x180009670  test    r9, r9
0x180009673  jnz     short loc_18000967E
0x180009675  lea     ecx, [r9+7Ah]
0x180009679  jmp     loc_1800099E8
0x18000967e  mov     ebx, ecx
0x180009680  test    r12, r12
0x180009683  jz      short loc_18000968D
0x180009685  mov     rax, [r8]
0x180009688  mov     [rsp+0B8h+OutBuffer], rax
0x18000968d  mov     esi, ecx
0x18000968f  mov     r14d, ecx
0x180009692  cmp     cx, r15w
0x180009696  jnb     loc_18000977B
0x18000969c  mov     r13d, 6
0x1800096a2  movzx   eax, si
0x1800096a5  mov     rdi, [r9+rax*8]
0x1800096a9  test    rdi, rdi
0x1800096ac  jz      loc_1800099E3
0x1800096b2  cmp     cx, [rdi]
0x1800096b5  jz      loc_1800099E3
0x1800096bb  mov     r8d, r13d; MaxCount
0x1800096be  lea     rdx, aBlf; "%BLF%\\"
0x1800096c5  mov     rcx, rdi; String1
0x1800096c8  call    wcsncmp_0
0x1800096cd  xor     ecx, ecx
0x1800096cf  test    eax, eax
0x1800096d1  jz      short loc_18000973C
0x1800096d3  mov     r8d, r13d; MaxCount
0x1800096d6  lea     rdx, aBlf_0; "%BLF%:"
0x1800096dd  mov     rcx, rdi; String1
0x1800096e0  call    wcsncmp_0
0x1800096e5  xor     ecx, ecx
0x1800096e7  test    eax, eax
0x1800096e9  jz      short loc_18000973C
0x1800096eb  xorps   xmm0, xmm0
0x1800096ee  movups  xmmword ptr [rsp+0B8h+NtName.Length], xmm0
0x1800096f3  xor     r9d, r9d; RelativeName
0x1800096f6  xor     r8d, r8d; PartName
0x1800096f9  lea     rdx, [rsp+0B8h+NtName]; NtName
0x1800096fe  mov     rcx, rdi; DosName
0x180009701  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180009708  nop     dword ptr [rax+rax+00h]
0x18000970d  mov     rcx, gs:60h
0x180009716  xor     edx, edx; Flags
0x180009718  mov     r8, [rsp+0B8h+NtName.Buffer]; P
0x18000971d  mov     rcx, [rcx+30h]; HeapHandle
0x180009721  test    al, al
0x180009723  jz      short loc_180009765
0x180009725  movzx   ebx, [rsp+0B8h+NtName.Length]
0x18000972a  shr     ebx, 1
0x18000972c  call    cs:__imp_RtlFreeHeap
0x180009733  nop     dword ptr [rax+rax+00h]
0x180009738  xor     ecx, ecx
0x18000973a  jmp     short loc_180009749
0x18000973c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009740  inc     rbx
0x180009743  cmp     [rdi+rbx*2], cx
0x180009747  jnz     short loc_180009740
0x180009749  inc     r14d
0x18000974c  add     r14d, ebx
0x18000974f  inc     si
0x180009752  cmp     si, r15w
0x180009756  jnb     short loc_18000977B
0x180009758  mov     r9, [rsp+0B8h+arg_18]
0x180009760  jmp     loc_1800096A2
0x180009765  call    cs:__imp_RtlFreeHeap
0x18000976c  nop     dword ptr [rax+rax+00h]
0x180009771  mov     ecx, 3
0x180009776  jmp     loc_1800099E8
0x18000977b  lea     eax, [r14+r15]
0x18000977f  lea     r14d, ds:10h[rax*2]
0x180009787  mov     [rsp+0B8h+nInBufferSize], r14d
0x18000978c  mov     esi, r14d
0x18000978f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009796  mov     ecx, r14d; unsigned __int64
0x180009799  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000979e  mov     rdi, rax
0x1800097a1  xor     r14d, r14d
0x1800097a4  test    rax, rax
0x1800097a7  jnz     short loc_1800097B1
0x1800097a9  lea     ecx, [rax+8]
0x1800097ac  jmp     loc_1800099E8
0x1800097b1  mov     [rsp+0B8h+var_50], rdi
0x1800097b6  mov     r8, rsi; Size
0x1800097b9  xor     edx, edx; Val
0x1800097bb  mov     rcx, rdi; void *
0x1800097be  call    memset_0
0x1800097c3  nop
0x1800097c4  mov     [rdi+8], r15w
0x1800097c9  mov     rax, [rsp+0B8h+OutBuffer]
0x1800097ce  mov     [rdi], rax
0x1800097d1  lea     rax, [rsi-10h]
0x1800097d5  shr     rax, 1
0x1800097d8  mov     [rsp+0B8h+var_60], rax
0x1800097dd  mov     esi, r14d
0x1800097e0  mov     [rsp+0B8h+var_78], r14w
0x1800097e6  mov     r13d, r14d
0x1800097e9  cmp     si, r15w
0x1800097ed  jnb     loc_18000996F
0x1800097f3  movzx   eax, si
0x1800097f6  mov     rcx, [rsp+0B8h+arg_18]
0x1800097fe  mov     r14, [rcx+rax*8]
0x180009802  mov     r8d, 6; MaxCount
0x180009808  lea     rdx, aBlf; "%BLF%\\"
0x18000980f  mov     rcx, r14; String1
0x180009812  call    wcsncmp_0
0x180009817  xor     ecx, ecx
0x180009819  test    eax, eax
0x18000981b  jz      loc_18000991D
0x180009821  lea     r8d, [rcx+6]; MaxCount
0x180009825  lea     rdx, aBlf_0; "%BLF%:"
0x18000982c  mov     rcx, r14; String1
0x18000982f  call    wcsncmp_0
0x180009834  xor     ecx, ecx
0x180009836  test    eax, eax
0x180009838  jz      loc_18000991D
0x18000983e  xorps   xmm0, xmm0
0x180009841  movups  xmmword ptr [rsp+0B8h+NtName.Length], xmm0
0x180009846  xor     r9d, r9d; RelativeName
0x180009849  xor     r8d, r8d; PartName
0x18000984c  lea     rdx, [rsp+0B8h+NtName]; NtName
0x180009851  mov     rcx, r14; DosName
0x180009854  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18000985b  nop     dword ptr [rax+rax+00h]
0x180009860  test    al, al
0x180009862  jnz     short loc_180009886
0x180009864  mov     ecx, 3; dwErrCode
0x180009869  call    cs:__imp_SetLastError
0x180009870  nop     dword ptr [rax+rax+00h]
0x180009875  lea     rdx, loc_1800099F4
0x18000987c  mov     rcx, [rsp+0B8h+var_58]
0x180009881  call    _local_unwind_0
0x180009886  movzx   ecx, [rsp+0B8h+NtName.Length]
0x18000988b  shr     ecx, 1
0x18000988d  mov     ebx, ecx
0x18000988f  mov     [rsp+0B8h+var_74], ecx
0x180009893  mov     eax, dword ptr [rsp+0B8h+var_60]
0x180009897  sub     eax, r13d
0x18000989a  cmp     eax, ecx
0x18000989c  jnb     short loc_1800098E0
0x18000989e  mov     rcx, gs:60h
0x1800098a7  mov     r8, [rsp+0B8h+NtName.Buffer]; P
0x1800098ac  xor     edx, edx; Flags
0x1800098ae  mov     rcx, [rcx+30h]; HeapHandle
0x1800098b2  call    cs:__imp_RtlFreeHeap
0x1800098b9  nop     dword ptr [rax+rax+00h]
0x1800098be  mov     ecx, 54Fh; dwErrCode
0x1800098c3  call    cs:__imp_SetLastError
0x1800098ca  nop     dword ptr [rax+rax+00h]
0x1800098cf  lea     rdx, loc_1800099F4
0x1800098d6  mov     rcx, [rsp+0B8h+var_58]
0x1800098db  call    _local_unwind_0
0x1800098e0  mov     r8d, ecx
0x1800098e3  add     r8, r8; Size
0x1800098e6  mov     eax, r13d
0x1800098e9  add     rax, 8
0x1800098ed  lea     rcx, [rdi+rax*2]; void *
0x1800098f1  mov     rdx, [rsp+0B8h+NtName.Buffer]; Src
0x1800098f6  call    memcpy_0
0x1800098fb  mov     rcx, gs:60h
0x180009904  mov     r8, [rsp+0B8h+NtName.Buffer]; P
0x180009909  xor     edx, edx; Flags
0x18000990b  mov     rcx, [rcx+30h]; HeapHandle
0x18000990f  call    cs:__imp_RtlFreeHeap
0x180009916  nop     dword ptr [rax+rax+00h]
0x18000991b  jmp     short loc_18000995C
0x18000991d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009921  inc     r8
0x180009924  cmp     [r14+r8*2], cx
0x180009929  jnz     short loc_180009921
0x18000992b  lea     r8, ds:2[r8*2]; Size
0x180009933  mov     eax, r13d
0x180009936  add     rax, 8
0x18000993a  lea     rcx, [rdi+rax*2]; void *
0x18000993e  mov     rdx, r14; Src
0x180009941  call    memcpy_0
0x180009946  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000994a  xor     ecx, ecx
0x18000994c  inc     rax
0x18000994f  cmp     [r14+rax*2], cx
0x180009954  jnz     short loc_18000994C
0x180009956  add     ebx, eax
0x180009958  mov     [rsp+0B8h+var_74], ebx
0x18000995c  inc     r13d
0x18000995f  add     r13d, ebx
0x180009962  inc     si
0x180009965  mov     [rsp+0B8h+var_78], si
0x18000996a  jmp     loc_1800097E9
0x18000996f  mov     rax, [rsp+0B8h+pReserved]
0x180009977  mov     [rsp+0B8h+lpOverlapped], rax; lpOverlapped
0x18000997c  lea     rax, [rsp+0B8h+BytesReturned]
0x180009984  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x180009989  mov     [rsp+0B8h+nOutBufferSize], 8; nOutBufferSize
0x180009991  lea     rax, [rsp+0B8h+OutBuffer]
0x180009996  mov     [rsp+0B8h+lpOutBuffer], rax; lpOutBuffer
0x18000999b  mov     r9d, [rsp+0B8h+nInBufferSize]; nInBufferSize
0x1800099a0  mov     r8, rdi; lpInBuffer
0x1800099a3  mov     edx, 8007A808h; dwIoControlCode
0x1800099a8  mov     rcx, [rsp+0B8h+hDevice]; hDevice
0x1800099b0  call    cs:__imp_DeviceIoControl
0x1800099b7  nop     dword ptr [rax+rax+00h]
0x1800099bc  mov     ebx, eax
0x1800099be  test    eax, eax
0x1800099c0  jz      short loc_1800099D0
0x1800099c2  test    r12, r12
0x1800099c5  jz      short loc_1800099D0
0x1800099c7  mov     rdx, [rsp+0B8h+OutBuffer]
0x1800099cc  mov     [r12], rdx
0x1800099d0  mov     rcx, rdi
0x1800099d3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800099da  nop     dword ptr [rax+rax+00h]
0x1800099df  mov     eax, ebx
0x1800099e1  jmp     short loc_1800099F6
0x1800099e3  mov     ecx, 57h ; 'W'; dwErrCode
0x1800099e8  call    cs:__imp_SetLastError
0x1800099ef  nop     dword ptr [rax+rax+00h]
0x1800099f4  xor     eax, eax
0x1800099f6  add     rsp, 80h
0x1800099fd  pop     r15
0x1800099ff  pop     r14
0x180009a01  pop     r13
0x180009a03  pop     r12
0x180009a05  pop     rdi
0x180009a06  pop     rsi
0x180009a07  pop     rbx
0x180009a08  retn
0x180015285  push    rbp
0x180015287  sub     rsp, 40h
0x18001528b  mov     rbp, rdx
0x18001528e  mov     rcx, [rbp+68h]
0x180015292  test    rcx, rcx
0x180015295  jz      short loc_1800152A4
0x180015297  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001529e  nop     dword ptr [rax+rax+00h]
0x1800152a3  nop
0x1800152a4  add     rsp, 40h
0x1800152a8  pop     rbp
0x1800152a9  retn
```
