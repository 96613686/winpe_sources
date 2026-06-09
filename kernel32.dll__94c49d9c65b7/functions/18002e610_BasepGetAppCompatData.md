# BasepGetAppCompatData

- ea: `0x18002e610`
- end: `0x18002eaf4`
- name: `BasepGetAppCompatData`
- size: `1252`
- prototype: `__int64 __fastcall(wchar_t *Str, _WORD *, _DWORD *, __int64, _WORD *, __int64 *, __int64, unsigned __int16, __int64, int, _OWORD **, _DWORD *, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002e610`
- `0x18002eafc`
- `0x18002ee6c`
- `0x1800593a0`
- `0x18005c3a8`
- `0x18005c3cc`
- `0x18005c468`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x18002ea5f`
- `ntdll!RtlDecodeSystemPointer` at `0x18002eab2`
- `ntdll!RtlDecodeSystemPointer` at `0x18002eac3`
- `ntdll!RtlDecodeSystemPointer` at `0x18002ead4`
- `ntdll!RtlDecodeSystemPointer` at `0x18002eae5`
- `ntdll!RtlDecodeSystemPointer` at `0x18002ea5f`
- `ntdll!RtlDecodeSystemPointer` at `0x18002eab2`
- `ntdll!RtlDecodeSystemPointer` at `0x18002eac3`
- `ntdll!RtlDecodeSystemPointer` at `0x18002ead4`
- `ntdll!RtlDecodeSystemPointer` at `0x18002eae5`
- `ntdll!wcsncpy_s` at `0x18002e791`
- `ntdll!wcsncpy_s` at `0x18002e791`
- `ntdll!RtlFreeHeap` at `0x18002e8d0`
- `ntdll!RtlFreeHeap` at `0x18002e8d0`
- `ntdll!RtlAllocateHeap` at `0x18002e68c`
- `ntdll!RtlAllocateHeap` at `0x18002e68c`

## pseudocode

```c
__int64 __fastcall BasepGetAppCompatData(
        wchar_t *Str,
        _WORD *a2,
        _DWORD *a3,
        __int64 a4,
        _WORD *a5,
        __int64 *a6,
        __int64 a7,
        unsigned __int16 a8,
        __int64 a9,
        int a10,
        _OWORD **a11,
        _DWORD *a12,
        _QWORD *a13,
        _DWORD *a14)
{
  int v14; // ebx
  _DWORD *Heap; // rax
  unsigned int v19; // r14d
  __int64 v20; // r13
  unsigned __int16 v21; // cx
  int v22; // ecx
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // r8
  const wchar_t *Buffer; // r8
  _QWORD *v25; // rsi
  _DWORD *v26; // r12
  _OWORD *v27; // rcx
  wchar_t *v28; // rax
  const wchar_t *v29; // rdi
  int v30; // eax
  unsigned int v31; // edi
  __int64 v32; // rax
  _QWORD *v33; // r8
  unsigned int i; // ecx
  __int64 v35; // rdx
  __int64 v36; // rax
  PVOID v37; // rax
  int v38; // edx
  __int64 result; // rax
  __int64 v40; // rax
  _OWORD *v41; // rdx
  __int128 v42; // xmm1
  PVOID v43; // rax
  int v44; // [rsp+40h] [rbp-61h] BYREF
  PVOID P; // [rsp+48h] [rbp-59h] BYREF
  __int128 v46; // [rsp+50h] [rbp-51h] BYREF
  __int128 v47; // [rsp+60h] [rbp-41h]
  __int64 v48; // [rsp+70h] [rbp-31h] BYREF
  int v49; // [rsp+78h] [rbp-29h]
  int v50; // [rsp+7Ch] [rbp-25h]
  PVOID v51; // [rsp+80h] [rbp-21h]
  __int16 v52; // [rsp+88h] [rbp-19h]
  __int16 v53; // [rsp+8Ah] [rbp-17h]
  __int16 v54; // [rsp+8Ch] [rbp-15h]
  __int16 v55; // [rsp+8Eh] [rbp-13h]
  _WORD *v56; // [rsp+90h] [rbp-11h]
  SIZE_T Size; // [rsp+100h] [rbp+5Fh] BYREF

  v14 = (*a3 >> 2) & 1;
  P = 0;
  LODWORD(Size) = 4568;
  v50 = 0;
  v44 = 0;
  v46 = 0;
  v47 = 0;
  if ( (unsigned int)RtlGetCurrentServiceSessionId_0() && (int)RtlpQueryContainersCompatMode(&v44) >= 0 && v44 )
    v14 |= 4u;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
  P = Heap;
  v19 = 0;
  if ( !Heap )
    goto LABEL_28;
  v20 = a7;
  Heap[130] = Size;
  v21 = a8;
  *((_DWORD *)P + 131) = -1408373333;
  *((_WORD *)P + 266) = v21;
  *((_DWORD *)P + 1105) = *(_DWORD *)(v20 + 56);
  *((_DWORD *)P + 1106) = *(_DWORD *)(v20 + 60);
  if ( !a2 || (v22 = 1, !*a2) )
    v22 = 0;
  *((_DWORD *)P + 1108) = v22;
  *((_DWORD *)P + 1109) = *a5 != 0;
  *((_DWORD *)P + 1110) = *(_DWORD *)(a4 + 4) != 0;
  *((_DWORD *)P + 1111) = v14 != 0;
  *((_DWORD *)P + 1112) = *(_DWORD *)(a4 + 4);
  *((_DWORD *)P + 718) = NtCurrentTeb()->ClientId.UniqueProcess;
  ProcessParameters = NtCurrentPeb()->ProcessParameters;
  if ( ProcessParameters )
  {
    Buffer = ProcessParameters->ImagePathName.Buffer;
    if ( Buffer )
      wcsncpy_s((wchar_t *)P + 1438, 0x104u, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
  }
  v25 = a11;
  v26 = a12;
  v27 = *a11;
  if ( *a11 && *a12 == 456 )
  {
    v40 = 3;
    v41 = (char *)P + 536;
    do
    {
      *v41 = *v27;
      v41[1] = v27[1];
      v41[2] = v27[2];
      v41[3] = v27[3];
      v41[4] = v27[4];
      v41[5] = v27[5];
      v41[6] = v27[6];
      v42 = v27[7];
      v27 += 8;
      v41[7] = v42;
      v41 += 8;
      --v40;
    }
    while ( v40 );
    *v41 = *v27;
    v41[1] = v27[1];
    v41[2] = v27[2];
    v41[3] = v27[3];
    *((_QWORD *)v41 + 8) = *((_QWORD *)v27 + 8);
  }
  v28 = wcsrchr_0(Str, 0x5Cu);
  if ( v28 )
    v29 = v28 + 1;
  else
    v29 = Str;
  if ( !wcsicmp_0(v29, L"wwahost.exe")
    || !wcsicmp_0(v29, L"microsoftedge.exe")
    || !wcsicmp_0(v29, L"microsoftedgecp.exe")
    || !wcsicmp_0(v29, L"microsoftedgebchost.exe")
    || !wcsicmp_0(v29, L"microsoftedgedevtools.exe") )
  {
    v14 |= 2u;
  }
  v30 = wcsicmp_0(v29, L"msedgewebview2.exe");
  v31 = v14 | 8;
  v51 = P;
  if ( v30 )
    v31 = v14;
  v52 = *(_WORD *)(v20 + 38);
  v53 = *(_WORD *)(v20 + 36);
  v54 = *(_WORD *)(v20 + 40);
  v55 = *(_WORD *)(v20 + 42);
  v56 = a5;
  v32 = a9;
  if ( *a6 )
    v32 = *a6;
  v48 = v32;
  v49 = a10;
  if ( *v25 )
  {
    if ( (int)BasepInitializeApphelpGlobals() < 0 )
      goto LABEL_28;
    *(_QWORD *)&v46 = RtlDecodeSystemPointer(qword_1800B6070);
    *((_QWORD *)&v46 + 1) = RtlDecodeSystemPointer(qword_1800B6078);
    *(_QWORD *)&v47 = RtlDecodeSystemPointer(qword_1800B6080);
    *((_QWORD *)&v47 + 1) = RtlDecodeSystemPointer(qword_1800B6088);
  }
  if ( (int)SbPrepareSwitchContext(&v48, &v46) >= 0 )
  {
    v33 = (char *)P + 2064;
    if ( P != (PVOID)-2064LL )
    {
      for ( i = 0; i < 5; ++i )
      {
        v35 = 32LL * i;
        v36 = *v33 - *(_QWORD *)&SbSupportedOsList[v35 + 4];
        if ( *v33 == *(_QWORD *)&SbSupportedOsList[v35 + 4] )
          v36 = *((_QWORD *)P + 259) - *(_QWORD *)&SbSupportedOsList[v35 + 12];
        if ( !v36 )
        {
          *((_DWORD *)P + 1107) = *(_DWORD *)&SbSupportedOsList[v35] == 4;
          if ( (v31 || *v25) && (int)BasepInitializeApphelpGlobals() >= 0 )
          {
            v43 = RtlDecodeSystemPointer(Pointer);
            if ( v43 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD *, _DWORD *, PVOID *, SIZE_T *))v43)(
                a8,
                v31,
                v25,
                v26,
                &P,
                &Size);
          }
          v19 = 1;
          v37 = P;
          v38 = Size;
          goto LABEL_29;
        }
      }
    }
  }
LABEL_28:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  v37 = 0;
  v38 = 0;
LABEL_29:
  *a13 = v37;
  result = v19;
  *a14 = v38;
  return result;
}

```

## disassembly

```asm
0x18002e610  push    rbp
0x18002e612  push    rbx
0x18002e613  push    rsi
0x18002e614  push    rdi
0x18002e615  push    r12
0x18002e617  push    r13
0x18002e619  push    r14
0x18002e61b  push    r15
0x18002e61d  lea     rbp, [rsp-7]
0x18002e622  sub     rsp, 0A8h
0x18002e629  mov     ebx, [r8]
0x18002e62c  xor     r12d, r12d
0x18002e62f  xorps   xmm0, xmm0
0x18002e632  shr     ebx, 2
0x18002e635  and     ebx, 1
0x18002e638  mov     [rbp+3Fh+P], r12
0x18002e63c  mov     rsi, r9
0x18002e63f  mov     dword ptr [rbp+3Fh+Size], 11D8h
0x18002e646  mov     rdi, rdx
0x18002e649  mov     [rbp+3Fh+var_64], r12d
0x18002e64d  mov     r15, rcx
0x18002e650  mov     [rbp+3Fh+var_A0], r12d
0x18002e654  movups  [rbp+3Fh+var_90], xmm0
0x18002e658  movups  [rbp+3Fh+var_80], xmm0
0x18002e65c  call    RtlGetCurrentServiceSessionId_0
0x18002e661  test    eax, eax
0x18002e663  jz      short loc_18002E676
0x18002e665  lea     rcx, [rbp+3Fh+var_A0]
0x18002e669  call    RtlpQueryContainersCompatMode
0x18002e66e  test    eax, eax
0x18002e670  jns     loc_18002EA99
0x18002e676  mov     rcx, gs:60h
0x18002e67f  mov     edx, 8; Flags
0x18002e684  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x18002e688  mov     rcx, [rcx+30h]; HeapHandle
0x18002e68c  call    cs:__imp_RtlAllocateHeap
0x18002e692  mov     [rbp+3Fh+P], rax
0x18002e696  mov     rcx, rax
0x18002e699  mov     r14d, r12d
0x18002e69c  test    rax, rax
0x18002e69f  jz      loc_18002E8BD
0x18002e6a5  mov     eax, dword ptr [rbp+3Fh+Size]
0x18002e6a8  mov     r13, [rbp+3Fh+arg_30]
0x18002e6ac  mov     [rcx+208h], eax
0x18002e6b2  mov     rax, [rbp+3Fh+P]
0x18002e6b6  movzx   ecx, [rbp+3Fh+arg_38]
0x18002e6bd  mov     dword ptr [rax+20Ch], 0AC0DEDABh
0x18002e6c7  mov     rax, [rbp+3Fh+P]
0x18002e6cb  mov     [rax+214h], cx
0x18002e6d2  mov     rax, [rbp+3Fh+P]
0x18002e6d6  mov     ecx, [r13+38h]
0x18002e6da  mov     [rax+1144h], ecx
0x18002e6e0  mov     rax, [rbp+3Fh+P]
0x18002e6e4  mov     ecx, [r13+3Ch]
0x18002e6e8  mov     [rax+1148h], ecx
0x18002e6ee  test    rdi, rdi
0x18002e6f1  jnz     loc_18002E9A0
0x18002e6f7  mov     ecx, r12d
0x18002e6fa  mov     rax, [rbp+3Fh+P]
0x18002e6fe  mov     [rax+1150h], ecx
0x18002e704  mov     ecx, r12d
0x18002e707  mov     rax, [rbp+3Fh+arg_20]
0x18002e70b  cmp     [rax], r12w
0x18002e70f  mov     rax, [rbp+3Fh+P]
0x18002e713  setnz   cl
0x18002e716  mov     [rax+1154h], ecx
0x18002e71c  mov     ecx, r12d
0x18002e71f  cmp     [rsi+4], r12d
0x18002e723  mov     rax, [rbp+3Fh+P]
0x18002e727  setnz   cl
0x18002e72a  test    ebx, ebx
0x18002e72c  mov     [rax+1158h], ecx
0x18002e732  mov     ecx, r12d
0x18002e735  mov     rax, [rbp+3Fh+P]
0x18002e739  setnz   cl
0x18002e73c  mov     [rax+115Ch], ecx
0x18002e742  mov     rax, [rbp+3Fh+P]
0x18002e746  mov     ecx, [rsi+4]
0x18002e749  mov     [rax+1160h], ecx
0x18002e74f  mov     rcx, gs:40h
0x18002e758  mov     rax, [rbp+3Fh+P]
0x18002e75c  mov     [rax+0B38h], ecx
0x18002e762  mov     rax, gs:60h
0x18002e76b  mov     r8, [rax+20h]
0x18002e76f  test    r8, r8
0x18002e772  jz      short loc_18002E797
0x18002e774  mov     r8, [r8+68h]; Source
0x18002e778  test    r8, r8
0x18002e77b  jz      short loc_18002E797
0x18002e77d  mov     rcx, [rbp+3Fh+P]
0x18002e781  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002e785  add     rcx, 0B3Ch; Destination
0x18002e78c  mov     edx, 104h; SizeInWords
0x18002e791  call    cs:__imp_wcsncpy_s
0x18002e797  mov     rsi, [rbp+3Fh+arg_50]
0x18002e79e  mov     r12, [rbp+3Fh+arg_58]
0x18002e7a5  mov     rcx, [rsi]
0x18002e7a8  test    rcx, rcx
0x18002e7ab  jnz     loc_18002E9B4
0x18002e7b1  mov     edx, 5Ch ; '\'; Ch
0x18002e7b6  mov     rcx, r15; Str
0x18002e7b9  call    wcsrchr_0
0x18002e7be  mov     rdi, rax
0x18002e7c1  test    rax, rax
0x18002e7c4  jz      loc_18002E998
0x18002e7ca  add     rdi, 2
0x18002e7ce  lea     rdx, aWwahostExe; "wwahost.exe"
0x18002e7d5  mov     rcx, rdi; String1
0x18002e7d8  call    _wcsicmp_0
0x18002e7dd  test    eax, eax
0x18002e7df  jnz     loc_18002E937
0x18002e7e5  or      ebx, 2
0x18002e7e8  lea     rdx, aMsedgewebview2; "msedgewebview2.exe"
0x18002e7ef  mov     rcx, rdi; String1
0x18002e7f2  call    _wcsicmp_0
0x18002e7f7  mov     edi, ebx
0x18002e7f9  or      edi, 8
0x18002e7fc  test    eax, eax
0x18002e7fe  mov     rax, [rbp+3Fh+P]
0x18002e802  mov     [rbp+3Fh+var_60], rax
0x18002e806  movzx   eax, word ptr [r13+26h]
0x18002e80b  cmovnz  edi, ebx
0x18002e80e  mov     [rbp+3Fh+var_58], ax
0x18002e812  movzx   eax, word ptr [r13+24h]
0x18002e817  mov     [rbp+3Fh+var_56], ax
0x18002e81b  movzx   eax, word ptr [r13+28h]
0x18002e820  mov     [rbp+3Fh+var_54], ax
0x18002e824  movzx   eax, word ptr [r13+2Ah]
0x18002e829  mov     [rbp+3Fh+var_52], ax
0x18002e82d  mov     rax, [rbp+3Fh+arg_20]
0x18002e831  mov     [rbp+3Fh+var_50], rax
0x18002e835  mov     rax, [rbp+3Fh+arg_28]
0x18002e839  mov     rcx, [rax]
0x18002e83c  mov     rax, [rbp+3Fh+arg_40]
0x18002e843  test    rcx, rcx
0x18002e846  cmovnz  rax, rcx
0x18002e84a  mov     [rbp+3Fh+var_70], rax
0x18002e84e  mov     eax, [rbp+3Fh+arg_48]
0x18002e854  mov     [rbp+3Fh+var_68], eax
0x18002e857  cmp     [rsi], r14
0x18002e85a  jnz     short loc_18002E8AD
0x18002e85c  lea     rdx, [rbp+3Fh+var_90]
0x18002e860  lea     rcx, [rbp+3Fh+var_70]
0x18002e864  call    SbPrepareSwitchContext
0x18002e869  test    eax, eax
0x18002e86b  js      short loc_18002E8BA
0x18002e86d  mov     r9, [rbp+3Fh+P]
0x18002e871  lea     r8, [r9+810h]
0x18002e878  test    r8, r8
0x18002e87b  jz      short loc_18002E8BA
0x18002e87d  xor     ecx, ecx
0x18002e87f  lea     r10, SbSupportedOsList
0x18002e886  cmp     ecx, 5
0x18002e889  jnb     short loc_18002E8BA
0x18002e88b  mov     rax, [r8]
0x18002e88e  mov     edx, ecx
0x18002e890  shl     rdx, 5
0x18002e894  sub     rax, [rdx+r10+4]
0x18002e899  jnz     short loc_18002E8A4
0x18002e89b  mov     rax, [r8+8]
0x18002e89f  sub     rax, [rdx+r10+0Ch]
0x18002e8a4  test    rax, rax
0x18002e8a7  jz      short loc_18002E906
0x18002e8a9  inc     ecx
0x18002e8ab  jmp     short loc_18002E886
0x18002e8ad  call    BasepInitializeApphelpGlobals
0x18002e8b2  test    eax, eax
0x18002e8b4  jns     loc_18002EAAB
0x18002e8ba  xor     r12d, r12d
0x18002e8bd  mov     rcx, gs:60h
0x18002e8c6  xor     edx, edx; Flags
0x18002e8c8  mov     r8, [rbp+3Fh+P]; P
0x18002e8cc  mov     rcx, [rcx+30h]; HeapHandle
0x18002e8d0  call    cs:__imp_RtlFreeHeap
0x18002e8d6  mov     rax, r12
0x18002e8d9  mov     edx, r12d
0x18002e8dc  mov     rcx, [rbp+3Fh+arg_60]
0x18002e8e3  mov     [rcx], rax
0x18002e8e6  mov     eax, r14d
0x18002e8e9  mov     rcx, [rbp+3Fh+arg_68]
0x18002e8f0  mov     [rcx], edx
0x18002e8f2  add     rsp, 0A8h
0x18002e8f9  pop     r15
0x18002e8fb  pop     r14
0x18002e8fd  pop     r13
0x18002e8ff  pop     r12
0x18002e901  pop     rdi
0x18002e902  pop     rsi
0x18002e903  pop     rbx
0x18002e904  pop     rbp
0x18002e905  retn
0x18002e906  xor     eax, eax
0x18002e908  cmp     dword ptr [rdx+r10], 4
0x18002e90d  setz    al
0x18002e910  mov     [r9+114Ch], eax
0x18002e917  test    edi, edi
0x18002e919  jnz     loc_18002EA4B
0x18002e91f  cmp     [rsi], r14
0x18002e922  jnz     loc_18002EA4B
0x18002e928  mov     r14d, 1
0x18002e92e  mov     rax, [rbp+3Fh+P]
0x18002e932  mov     edx, dword ptr [rbp+3Fh+Size]
0x18002e935  jmp     short loc_18002E8DC
0x18002e937  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x18002e93e  mov     rcx, rdi; String1
0x18002e941  call    _wcsicmp_0
0x18002e946  test    eax, eax
0x18002e948  jz      loc_18002E7E5
0x18002e94e  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x18002e955  mov     rcx, rdi; String1
0x18002e958  call    _wcsicmp_0
0x18002e95d  test    eax, eax
0x18002e95f  jz      loc_18002E7E5
0x18002e965  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x18002e96c  mov     rcx, rdi; String1
0x18002e96f  call    _wcsicmp_0
0x18002e974  test    eax, eax
0x18002e976  jz      loc_18002E7E5
0x18002e97c  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x18002e983  mov     rcx, rdi; String1
0x18002e986  call    _wcsicmp_0
0x18002e98b  test    eax, eax
0x18002e98d  jnz     loc_18002E7E8
0x18002e993  jmp     loc_18002E7E5
0x18002e998  mov     rdi, r15
0x18002e99b  jmp     loc_18002E7CE
0x18002e9a0  mov     ecx, 1
0x18002e9a5  cmp     [rdi], r12w
0x18002e9a9  jnz     loc_18002E6FA
0x18002e9af  jmp     loc_18002E6F7
0x18002e9b4  cmp     dword ptr [r12], 1C8h
0x18002e9bc  jnz     loc_18002E7B1
0x18002e9c2  mov     rdx, [rbp+3Fh+P]
0x18002e9c6  mov     eax, 3
0x18002e9cb  add     rdx, 218h
0x18002e9d2  lea     r8d, [rax+7Dh]
0x18002e9d6  movups  xmm0, xmmword ptr [rcx]
0x18002e9d9  movups  xmmword ptr [rdx], xmm0
0x18002e9dc  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e9e0  movups  xmmword ptr [rdx+10h], xmm1
0x18002e9e4  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e9e8  movups  xmmword ptr [rdx+20h], xmm0
0x18002e9ec  movups  xmm1, xmmword ptr [rcx+30h]
0x18002e9f0  movups  xmmword ptr [rdx+30h], xmm1
0x18002e9f4  movups  xmm0, xmmword ptr [rcx+40h]
0x18002e9f8  movups  xmmword ptr [rdx+40h], xmm0
0x18002e9fc  movups  xmm1, xmmword ptr [rcx+50h]
0x18002ea00  movups  xmmword ptr [rdx+50h], xmm1
0x18002ea04  movups  xmm0, xmmword ptr [rcx+60h]
0x18002ea08  movups  xmmword ptr [rdx+60h], xmm0
0x18002ea0c  movups  xmm1, xmmword ptr [rcx+70h]
0x18002ea10  add     rcx, r8
0x18002ea13  movups  xmmword ptr [rdx+70h], xmm1
0x18002ea17  add     rdx, r8
0x18002ea1a  sub     rax, 1
0x18002ea1e  jnz     short loc_18002E9D6
0x18002ea20  movups  xmm0, xmmword ptr [rcx]
0x18002ea23  movups  xmmword ptr [rdx], xmm0
0x18002ea26  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ea2a  movups  xmmword ptr [rdx+10h], xmm1
0x18002ea2e  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ea32  movups  xmmword ptr [rdx+20h], xmm0
0x18002ea36  movups  xmm1, xmmword ptr [rcx+30h]
0x18002ea3a  movups  xmmword ptr [rdx+30h], xmm1
0x18002ea3e  mov     rax, [rcx+40h]
0x18002ea42  mov     [rdx+40h], rax
0x18002ea46  jmp     loc_18002E7B1
0x18002ea4b  call    BasepInitializeApphelpGlobals
0x18002ea50  test    eax, eax
0x18002ea52  js      loc_18002E928
0x18002ea58  mov     rcx, cs:Pointer; Pointer
0x18002ea5f  call    cs:__imp_RtlDecodeSystemPointer
0x18002ea65  test    rax, rax
0x18002ea68  jz      loc_18002E928
0x18002ea6e  lea     rcx, [rbp+3Fh+Size]
0x18002ea72  mov     r9, r12
0x18002ea75  mov     [rsp+0E0h+var_B8], rcx
0x18002ea7a  mov     r8, rsi
0x18002ea7d  lea     rcx, [rbp+3Fh+P]
0x18002ea81  mov     edx, edi
0x18002ea83  mov     [rsp+0E0h+var_C0], rcx
0x18002ea88  movzx   ecx, [rbp+3Fh+arg_38]
0x18002ea8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea94  jmp     loc_18002E928
0x18002ea99  cmp     [rbp+3Fh+var_A0], r12d
0x18002ea9d  jz      loc_18002E676
0x18002eaa3  or      ebx, 4
0x18002eaa6  jmp     loc_18002E676
0x18002eaab  mov     rcx, cs:qword_1800B6070; Pointer
0x18002eab2  call    cs:__imp_RtlDecodeSystemPointer
0x18002eab8  mov     rcx, cs:qword_1800B6078; Pointer
0x18002eabf  mov     qword ptr [rbp+3Fh+var_90], rax
0x18002eac3  call    cs:__imp_RtlDecodeSystemPointer
0x18002eac9  mov     rcx, cs:qword_1800B6080; Pointer
0x18002ead0  mov     qword ptr [rbp+3Fh+var_90+8], rax
0x18002ead4  call    cs:__imp_RtlDecodeSystemPointer
0x18002eada  mov     rcx, cs:qword_1800B6088; Pointer
0x18002eae1  mov     qword ptr [rbp+3Fh+var_80], rax
0x18002eae5  call    cs:__imp_RtlDecodeSystemPointer
0x18002eaeb  mov     qword ptr [rbp+3Fh+var_80+8], rax
  ... truncated ...
```
