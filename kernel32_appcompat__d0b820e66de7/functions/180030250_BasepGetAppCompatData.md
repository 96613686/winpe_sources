# BasepGetAppCompatData

- ea: `0x180030250`
- end: `0x180030765`
- name: `BasepGetAppCompatData`
- size: `1301`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str@<rcx>, __int64, __int64, __int64, __int16, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180030250`
- `0x18003076c`
- `0x180030b60`
- `0x18005ead4`
- `0x180061d88`
- `0x180061dac`
- `0x180061e48`
- `0x180084010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x1800306b2`
- `ntdll!RtlDecodeSystemPointer` at `0x18003070b`
- `ntdll!RtlDecodeSystemPointer` at `0x180030722`
- `ntdll!RtlDecodeSystemPointer` at `0x180030739`
- `ntdll!RtlDecodeSystemPointer` at `0x180030750`
- `ntdll!RtlDecodeSystemPointer` at `0x1800306b2`
- `ntdll!RtlDecodeSystemPointer` at `0x18003070b`
- `ntdll!RtlDecodeSystemPointer` at `0x180030722`
- `ntdll!RtlDecodeSystemPointer` at `0x180030739`
- `ntdll!RtlDecodeSystemPointer` at `0x180030750`
- `ntdll!wcsncpy_s` at `0x1800303d7`
- `ntdll!wcsncpy_s` at `0x1800303d7`
- `ntdll!RtlFreeHeap` at `0x18003051c`
- `ntdll!RtlFreeHeap` at `0x18003051c`
- `ntdll!RtlAllocateHeap` at `0x1800302cc`
- `ntdll!RtlAllocateHeap` at `0x1800302cc`

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
    *(_QWORD *)&v46 = RtlDecodeSystemPointer(qword_1800BE070);
    *((_QWORD *)&v46 + 1) = RtlDecodeSystemPointer(qword_1800BE078);
    *(_QWORD *)&v47 = RtlDecodeSystemPointer(qword_1800BE080);
    *((_QWORD *)&v47 + 1) = RtlDecodeSystemPointer(qword_1800BE088);
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
0x180030250  push    rbp
0x180030252  push    rbx
0x180030253  push    rsi
0x180030254  push    rdi
0x180030255  push    r12
0x180030257  push    r13
0x180030259  push    r14
0x18003025b  push    r15
0x18003025d  lea     rbp, [rsp-7]
0x180030262  sub     rsp, 0A8h
0x180030269  mov     ebx, [r8]
0x18003026c  xor     r12d, r12d
0x18003026f  xorps   xmm0, xmm0
0x180030272  shr     ebx, 2
0x180030275  and     ebx, 1
0x180030278  mov     [rbp+3Fh+P], r12
0x18003027c  mov     rsi, r9
0x18003027f  mov     dword ptr [rbp+3Fh+Size], 11D8h
0x180030286  mov     rdi, rdx
0x180030289  mov     [rbp+3Fh+var_64], r12d
0x18003028d  mov     r15, rcx
0x180030290  mov     [rbp+3Fh+var_A0], r12d
0x180030294  movups  [rbp+3Fh+var_90], xmm0
0x180030298  movups  [rbp+3Fh+var_80], xmm0
0x18003029c  call    RtlGetCurrentServiceSessionId_0
0x1800302a1  test    eax, eax
0x1800302a3  jz      short loc_1800302B6
0x1800302a5  lea     rcx, [rbp+3Fh+var_A0]
0x1800302a9  call    RtlpQueryContainersCompatMode
0x1800302ae  test    eax, eax
0x1800302b0  jns     loc_1800306F2
0x1800302b6  mov     rcx, gs:60h
0x1800302bf  mov     edx, 8; Flags
0x1800302c4  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x1800302c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800302cc  call    cs:__imp_RtlAllocateHeap
0x1800302d3  nop     dword ptr [rax+rax+00h]
0x1800302d8  mov     [rbp+3Fh+P], rax
0x1800302dc  mov     rcx, rax
0x1800302df  mov     r14d, r12d
0x1800302e2  test    rax, rax
0x1800302e5  jz      loc_180030509
0x1800302eb  mov     eax, dword ptr [rbp+3Fh+Size]
0x1800302ee  mov     r13, [rbp+3Fh+arg_30]
0x1800302f2  mov     [rcx+208h], eax
0x1800302f8  mov     rax, [rbp+3Fh+P]
0x1800302fc  movzx   ecx, [rbp+3Fh+arg_38]
0x180030303  mov     dword ptr [rax+20Ch], 0AC0DEDABh
0x18003030d  mov     rax, [rbp+3Fh+P]
0x180030311  mov     [rax+214h], cx
0x180030318  mov     rax, [rbp+3Fh+P]
0x18003031c  mov     ecx, [r13+38h]
0x180030320  mov     [rax+1144h], ecx
0x180030326  mov     rax, [rbp+3Fh+P]
0x18003032a  mov     ecx, [r13+3Ch]
0x18003032e  mov     [rax+1148h], ecx
0x180030334  test    rdi, rdi
0x180030337  jnz     loc_1800305F3
0x18003033d  mov     ecx, r12d
0x180030340  mov     rax, [rbp+3Fh+P]
0x180030344  mov     [rax+1150h], ecx
0x18003034a  mov     ecx, r12d
0x18003034d  mov     rax, [rbp+3Fh+arg_20]
0x180030351  cmp     [rax], r12w
0x180030355  mov     rax, [rbp+3Fh+P]
0x180030359  setnz   cl
0x18003035c  mov     [rax+1154h], ecx
0x180030362  mov     ecx, r12d
0x180030365  cmp     [rsi+4], r12d
0x180030369  mov     rax, [rbp+3Fh+P]
0x18003036d  setnz   cl
0x180030370  test    ebx, ebx
0x180030372  mov     [rax+1158h], ecx
0x180030378  mov     ecx, r12d
0x18003037b  mov     rax, [rbp+3Fh+P]
0x18003037f  setnz   cl
0x180030382  mov     [rax+115Ch], ecx
0x180030388  mov     rax, [rbp+3Fh+P]
0x18003038c  mov     ecx, [rsi+4]
0x18003038f  mov     [rax+1160h], ecx
0x180030395  mov     rcx, gs:40h
0x18003039e  mov     rax, [rbp+3Fh+P]
0x1800303a2  mov     [rax+0B38h], ecx
0x1800303a8  mov     rax, gs:60h
0x1800303b1  mov     r8, [rax+20h]
0x1800303b5  test    r8, r8
0x1800303b8  jz      short loc_1800303E3
0x1800303ba  mov     r8, [r8+68h]; Source
0x1800303be  test    r8, r8
0x1800303c1  jz      short loc_1800303E3
0x1800303c3  mov     rcx, [rbp+3Fh+P]
0x1800303c7  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800303cb  add     rcx, 0B3Ch; Destination
0x1800303d2  mov     edx, 104h; SizeInWords
0x1800303d7  call    cs:__imp_wcsncpy_s
0x1800303de  nop     dword ptr [rax+rax+00h]
0x1800303e3  mov     rsi, [rbp+3Fh+arg_50]
0x1800303ea  mov     r12, [rbp+3Fh+arg_58]
0x1800303f1  mov     rcx, [rsi]
0x1800303f4  test    rcx, rcx
0x1800303f7  jnz     loc_180030607
0x1800303fd  mov     edx, 5Ch ; '\'; Ch
0x180030402  mov     rcx, r15; Str
0x180030405  call    wcsrchr_0
0x18003040a  mov     rdi, rax
0x18003040d  test    rax, rax
0x180030410  jz      loc_1800305EB
0x180030416  add     rdi, 2
0x18003041a  lea     rdx, aWwahostExe; "wwahost.exe"
0x180030421  mov     rcx, rdi; String1
0x180030424  call    _wcsicmp_0
0x180030429  test    eax, eax
0x18003042b  jnz     loc_18003058A
0x180030431  or      ebx, 2
0x180030434  lea     rdx, aMsedgewebview2; "msedgewebview2.exe"
0x18003043b  mov     rcx, rdi; String1
0x18003043e  call    _wcsicmp_0
0x180030443  mov     edi, ebx
0x180030445  or      edi, 8
0x180030448  test    eax, eax
0x18003044a  mov     rax, [rbp+3Fh+P]
0x18003044e  mov     [rbp+3Fh+var_60], rax
0x180030452  movzx   eax, word ptr [r13+26h]
0x180030457  cmovnz  edi, ebx
0x18003045a  mov     [rbp+3Fh+var_58], ax
0x18003045e  movzx   eax, word ptr [r13+24h]
0x180030463  mov     [rbp+3Fh+var_56], ax
0x180030467  movzx   eax, word ptr [r13+28h]
0x18003046c  mov     [rbp+3Fh+var_54], ax
0x180030470  movzx   eax, word ptr [r13+2Ah]
0x180030475  mov     [rbp+3Fh+var_52], ax
0x180030479  mov     rax, [rbp+3Fh+arg_20]
0x18003047d  mov     [rbp+3Fh+var_50], rax
0x180030481  mov     rax, [rbp+3Fh+arg_28]
0x180030485  mov     rcx, [rax]
0x180030488  mov     rax, [rbp+3Fh+arg_40]
0x18003048f  test    rcx, rcx
0x180030492  cmovnz  rax, rcx
0x180030496  mov     [rbp+3Fh+var_70], rax
0x18003049a  mov     eax, [rbp+3Fh+arg_48]
0x1800304a0  mov     [rbp+3Fh+var_68], eax
0x1800304a3  cmp     [rsi], r14
0x1800304a6  jnz     short loc_1800304F9
0x1800304a8  lea     rdx, [rbp+3Fh+var_90]
0x1800304ac  lea     rcx, [rbp+3Fh+var_70]
0x1800304b0  call    SbPrepareSwitchContext
0x1800304b5  test    eax, eax
0x1800304b7  js      short loc_180030506
0x1800304b9  mov     r9, [rbp+3Fh+P]
0x1800304bd  lea     r8, [r9+810h]
0x1800304c4  test    r8, r8
0x1800304c7  jz      short loc_180030506
0x1800304c9  xor     ecx, ecx
0x1800304cb  lea     r10, SbSupportedOsList
0x1800304d2  cmp     ecx, 5
0x1800304d5  jnb     short loc_180030506
0x1800304d7  mov     rax, [r8]
0x1800304da  mov     edx, ecx
0x1800304dc  shl     rdx, 5
0x1800304e0  sub     rax, [rdx+r10+4]
0x1800304e5  jnz     short loc_1800304F0
0x1800304e7  mov     rax, [r8+8]
0x1800304eb  sub     rax, [rdx+r10+0Ch]
0x1800304f0  test    rax, rax
0x1800304f3  jz      short loc_180030559
0x1800304f5  inc     ecx
0x1800304f7  jmp     short loc_1800304D2
0x1800304f9  call    BasepInitializeApphelpGlobals
0x1800304fe  test    eax, eax
0x180030500  jns     loc_180030704
0x180030506  xor     r12d, r12d
0x180030509  mov     rcx, gs:60h
0x180030512  xor     edx, edx; Flags
0x180030514  mov     r8, [rbp+3Fh+P]; P
0x180030518  mov     rcx, [rcx+30h]; HeapHandle
0x18003051c  call    cs:__imp_RtlFreeHeap
0x180030523  nop     dword ptr [rax+rax+00h]
0x180030528  mov     rax, r12
0x18003052b  mov     edx, r12d
0x18003052e  mov     rcx, [rbp+3Fh+arg_60]
0x180030535  mov     [rcx], rax
0x180030538  mov     eax, r14d
0x18003053b  mov     rcx, [rbp+3Fh+arg_68]
0x180030542  mov     [rcx], edx
0x180030544  add     rsp, 0A8h
0x18003054b  pop     r15
0x18003054d  pop     r14
0x18003054f  pop     r13
0x180030551  pop     r12
0x180030553  pop     rdi
0x180030554  pop     rsi
0x180030555  pop     rbx
0x180030556  pop     rbp
0x180030557  retn
0x180030559  xor     eax, eax
0x18003055b  cmp     dword ptr [rdx+r10], 4
0x180030560  setz    al
0x180030563  mov     [r9+114Ch], eax
0x18003056a  test    edi, edi
0x18003056c  jnz     loc_18003069E
0x180030572  cmp     [rsi], r14
0x180030575  jnz     loc_18003069E
0x18003057b  mov     r14d, 1
0x180030581  mov     rax, [rbp+3Fh+P]
0x180030585  mov     edx, dword ptr [rbp+3Fh+Size]
0x180030588  jmp     short loc_18003052E
0x18003058a  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x180030591  mov     rcx, rdi; String1
0x180030594  call    _wcsicmp_0
0x180030599  test    eax, eax
0x18003059b  jz      loc_180030431
0x1800305a1  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x1800305a8  mov     rcx, rdi; String1
0x1800305ab  call    _wcsicmp_0
0x1800305b0  test    eax, eax
0x1800305b2  jz      loc_180030431
0x1800305b8  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x1800305bf  mov     rcx, rdi; String1
0x1800305c2  call    _wcsicmp_0
0x1800305c7  test    eax, eax
0x1800305c9  jz      loc_180030431
0x1800305cf  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x1800305d6  mov     rcx, rdi; String1
0x1800305d9  call    _wcsicmp_0
0x1800305de  test    eax, eax
0x1800305e0  jnz     loc_180030434
0x1800305e6  jmp     loc_180030431
0x1800305eb  mov     rdi, r15
0x1800305ee  jmp     loc_18003041A
0x1800305f3  mov     ecx, 1
0x1800305f8  cmp     [rdi], r12w
0x1800305fc  jnz     loc_180030340
0x180030602  jmp     loc_18003033D
0x180030607  cmp     dword ptr [r12], 1C8h
0x18003060f  jnz     loc_1800303FD
0x180030615  mov     rdx, [rbp+3Fh+P]
0x180030619  mov     eax, 3
0x18003061e  add     rdx, 218h
0x180030625  lea     r8d, [rax+7Dh]
0x180030629  movups  xmm0, xmmword ptr [rcx]
0x18003062c  movups  xmmword ptr [rdx], xmm0
0x18003062f  movups  xmm1, xmmword ptr [rcx+10h]
0x180030633  movups  xmmword ptr [rdx+10h], xmm1
0x180030637  movups  xmm0, xmmword ptr [rcx+20h]
0x18003063b  movups  xmmword ptr [rdx+20h], xmm0
0x18003063f  movups  xmm1, xmmword ptr [rcx+30h]
0x180030643  movups  xmmword ptr [rdx+30h], xmm1
0x180030647  movups  xmm0, xmmword ptr [rcx+40h]
0x18003064b  movups  xmmword ptr [rdx+40h], xmm0
0x18003064f  movups  xmm1, xmmword ptr [rcx+50h]
0x180030653  movups  xmmword ptr [rdx+50h], xmm1
0x180030657  movups  xmm0, xmmword ptr [rcx+60h]
0x18003065b  movups  xmmword ptr [rdx+60h], xmm0
0x18003065f  movups  xmm1, xmmword ptr [rcx+70h]
0x180030663  add     rcx, r8
0x180030666  movups  xmmword ptr [rdx+70h], xmm1
0x18003066a  add     rdx, r8
0x18003066d  sub     rax, 1
0x180030671  jnz     short loc_180030629
0x180030673  movups  xmm0, xmmword ptr [rcx]
0x180030676  movups  xmmword ptr [rdx], xmm0
0x180030679  movups  xmm1, xmmword ptr [rcx+10h]
0x18003067d  movups  xmmword ptr [rdx+10h], xmm1
0x180030681  movups  xmm0, xmmword ptr [rcx+20h]
0x180030685  movups  xmmword ptr [rdx+20h], xmm0
0x180030689  movups  xmm1, xmmword ptr [rcx+30h]
0x18003068d  movups  xmmword ptr [rdx+30h], xmm1
0x180030691  mov     rax, [rcx+40h]
0x180030695  mov     [rdx+40h], rax
0x180030699  jmp     loc_1800303FD
0x18003069e  call    BasepInitializeApphelpGlobals
0x1800306a3  test    eax, eax
0x1800306a5  js      loc_18003057B
0x1800306ab  mov     rcx, cs:Pointer; Pointer
0x1800306b2  call    cs:__imp_RtlDecodeSystemPointer
0x1800306b9  nop     dword ptr [rax+rax+00h]
0x1800306be  test    rax, rax
0x1800306c1  jz      loc_18003057B
0x1800306c7  lea     rcx, [rbp+3Fh+Size]
0x1800306cb  mov     r9, r12
0x1800306ce  mov     [rsp+0E0h+var_B8], rcx
0x1800306d3  mov     r8, rsi
0x1800306d6  lea     rcx, [rbp+3Fh+P]
0x1800306da  mov     edx, edi
0x1800306dc  mov     [rsp+0E0h+var_C0], rcx
0x1800306e1  movzx   ecx, [rbp+3Fh+arg_38]
0x1800306e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306ed  jmp     loc_18003057B
0x1800306f2  cmp     [rbp+3Fh+var_A0], r12d
0x1800306f6  jz      loc_1800302B6
0x1800306fc  or      ebx, 4
0x1800306ff  jmp     loc_1800302B6
0x180030704  mov     rcx, cs:qword_1800BE070; Pointer
0x18003070b  call    cs:__imp_RtlDecodeSystemPointer
0x180030712  nop     dword ptr [rax+rax+00h]
0x180030717  mov     rcx, cs:qword_1800BE078; Pointer
0x18003071e  mov     qword ptr [rbp+3Fh+var_90], rax
0x180030722  call    cs:__imp_RtlDecodeSystemPointer
0x180030729  nop     dword ptr [rax+rax+00h]
0x18003072e  mov     rcx, cs:qword_1800BE080; Pointer
  ... truncated ...
```
