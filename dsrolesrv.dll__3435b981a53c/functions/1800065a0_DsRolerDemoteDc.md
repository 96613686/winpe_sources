# DsRolerDemoteDc

- ea: `0x1800065a0`
- end: `0x180006898`
- name: `DsRolerDemoteDc`
- size: `760`
- prototype: `__int64(int, const wchar_t *, unsigned int, const wchar_t *, ...)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task`

## callees

- `0x180003d84`
- `0x180003fb0`
- `0x180004ef8`
- `0x1800065a0`
- `0x18000e818`
- `0x18000f71c`
- `0x18000ffa8`
- `0x1800150cc`
- `0x180015ff0`
- `0x1800161a8`
- `0x18001f6c4`
- `0x180020b08`
- `0x180020dbc`

## import_xrefs

- `LSASRV!LsaISafeMode` at `0x18000664c`
- `LSASRV!LsaISafeMode` at `0x18000664c`

## string_xrefs

- `0x1800067c4`: `Start the worker task\n`

## pseudocode

```c
__int64 DsRolerDemoteDc(int a1, const wchar_t *a2, unsigned int a3, const wchar_t *a4, ...)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // r14d
  bool v8; // zf
  int v9; // esi
  __int64 v10; // r12
  int v11; // r15d
  unsigned int MachineType; // ebx
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  const wchar_t *v16; // r8
  const char *v17; // rbx
  const char *v18; // r8
  const char *v19; // r8
  __int64 v20; // [rsp+58h] [rbp-39h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-31h] BYREF
  __int128 v22; // [rsp+70h] [rbp-21h] BYREF
  _OWORD v23[4]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v27; // [rsp+F8h] [rbp+67h] BYREF
  va_list va; // [rsp+F8h] [rbp+67h]
  __int64 v29; // [rsp+100h] [rbp+6Fh]
  __int64 v30; // [rsp+108h] [rbp+77h]
  __int64 v31; // [rsp+110h] [rbp+7Fh]
  __int64 v32; // [rsp+118h] [rbp+87h]
  __int64 v33; // [rsp+120h] [rbp+8Fh]
  _QWORD *v34; // [rsp+128h] [rbp+97h]
  va_list va1; // [rsp+130h] [rbp+9Fh] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v27 = va_arg(va1, _QWORD);
  v29 = va_arg(va1, _QWORD);
  v30 = va_arg(va1, _QWORD);
  v31 = va_arg(va1, _QWORD);
  v32 = va_arg(va1, _QWORD);
  v33 = va_arg(va1, _QWORD);
  v34 = va_arg(va1, _QWORD *);
  v21[0] = v27;
  v21[1] = v33;
  v20 = 0;
  v22 = 0;
  v23[0] = 0;
  DsRolepDisableServiceStop();
  v7 = v29;
  if ( (_DWORD)v30 )
  {
    v8 = a3 == 1;
  }
  else
  {
    if ( a3 )
      goto LABEL_6;
    v8 = (v29 & 0x90000) == 0;
  }
  if ( v8 )
    return 87;
LABEL_6:
  v9 = v29 & 0x10000;
  if ( (v29 & 0x10000) != 0 && a3 == 1 )
    return 87;
  v10 = v32;
  v11 = v31;
  if ( !v32 )
  {
    if ( (_DWORD)v31 )
      return 87;
  }
  MachineType = DsRolepInitializeOperationHandle(v6, v5);
  if ( !MachineType )
  {
    if ( !(unsigned __int8)LsaISafeMode() || !v9 )
    {
      LODWORD(v27) = 0;
      MachineType = DsRolepGetMachineType((__int64 *)va);
      if ( MachineType )
      {
LABEL_33:
        DsRolepResetOperationHandle(0);
        goto LABEL_34;
      }
      v14 = (unsigned int)v27;
      if ( (unsigned int)v27 < 2 )
      {
        DsRolepLogPrintRoutine(4, "This operation is only valid on a domain controller\n");
        MachineType = 1352;
        goto LABEL_33;
      }
    }
    MachineType = DsRolepCheckClientAccess(DsRolepDemoteSD, v14, 1);
    if ( MachineType )
      goto LABEL_33;
    *v34 = 0;
    DsRolepInitializeLogHelper(1);
    DsRolepLogPrintRoutine(4, "Request for demotion of domain controller\n");
    v15 = a2;
    if ( !a2 )
      v15 = L"(NULL)";
    DsRolepLogPrintRoutine(4, "DnsDomainName  %ws\n", v15);
    DsRolepLogPrintRoutine(4, "\tServerRole  %lu\n", a3);
    v16 = a4;
    if ( !a4 )
      v16 = L"(NULL)";
    DsRolepLogPrintRoutine(4, "\tAccount %ws ", v16);
    DsRolepLogPrintRoutine(4, "\tOptions  %lu\n", v7);
    v17 = "TRUE";
    v18 = "TRUE";
    if ( !(_DWORD)v30 )
      v18 = "FALSE";
    DsRolepLogPrintRoutine(4, "\tLastDcInDomain  %S\n", v18);
    v19 = "TRUE";
    if ( !v9 )
      v19 = "FALSE";
    DsRolepLogPrintRoutine(4, "\tForced Demote  %S\n", v19);
    if ( (v7 & 0x80000) == 0 )
      v17 = "FALSE";
    DsRolepLogPrintRoutine(4, "\tStage 2 only   %S\n", v17);
    MachineType = DsRolepDecryptPasswordsWithKey(a1, (unsigned int)v21, 2, (unsigned int)&v22, 0);
    if ( MachineType )
      goto LABEL_33;
    DsRolepLogPrintRoutine(4, "Start the worker task\n");
    MachineType = DsRolepBuildDemoteArgumentBlock(a3, a2, a4, &v22, v7, (unsigned __int8)v30, v11, v10, v23, &v20);
    DsRolepFreePasswords(&v22, 2);
    if ( MachineType )
      goto LABEL_33;
    MachineType = DsRolepSpinWorkerThread(2, v20);
    if ( MachineType )
    {
      DsRolepFreeArgumentBlock(&v20, 0);
      goto LABEL_33;
    }
    *v34 = &DsRolepCurrentOperationHandle;
  }
LABEL_34:
  DsRolepLogPrintRoutine(4, "Request for demotion returning %lu\n", MachineType);
  return MachineType;
}

```

## disassembly

```asm
0x1800065a0  mov     rax, rsp
0x1800065a3  mov     [rax+20h], r9
0x1800065a7  mov     [rax+10h], rdx
0x1800065ab  mov     [rax+8], rcx
0x1800065af  push    rbp
0x1800065b0  push    rbx
0x1800065b1  push    rsi
0x1800065b2  push    rdi
0x1800065b3  push    r12
0x1800065b5  push    r14
0x1800065b7  push    r15
0x1800065b9  lea     rbp, [rax-3Fh]
0x1800065bd  sub     rsp, 90h
0x1800065c4  mov     rax, [rbp+37h+arg_20]
0x1800065c8  xorps   xmm0, xmm0
0x1800065cb  mov     [rbp+37h+var_68], rax
0x1800065cf  mov     edi, r8d
0x1800065d2  mov     rax, [rbp+37h+arg_48]
0x1800065d9  mov     [rbp+37h+var_60], rax
0x1800065dd  mov     [rbp+37h+var_70], 0
0x1800065e5  movups  [rbp+37h+var_58], xmm0
0x1800065e9  movups  [rbp+37h+var_48], xmm0
0x1800065ed  call    DsRolepDisableServiceStop
0x1800065f2  cmp     dword ptr [rbp+37h+arg_30], 0
0x1800065f6  mov     r14d, dword ptr [rbp+37h+arg_28]
0x1800065fa  jz      short loc_180006601
0x1800065fc  cmp     edi, 1
0x1800065ff  jmp     short loc_18000660C
0x180006601  test    edi, edi
0x180006603  jnz     short loc_18000660E
0x180006605  test    r14d, 90000h
0x18000660c  jz      short loc_180006633
0x18000660e  mov     esi, r14d
0x180006611  and     esi, 10000h
0x180006617  jz      short loc_18000661E
0x180006619  cmp     edi, 1
0x18000661c  jz      short loc_180006633
0x18000661e  mov     r12, [rbp+37h+arg_40]
0x180006625  mov     r15d, dword ptr [rbp+37h+arg_38]
0x180006629  test    r12, r12
0x18000662c  jnz     short loc_18000663D
0x18000662e  test    r15d, r15d
0x180006631  jz      short loc_18000663D
0x180006633  mov     eax, 57h ; 'W'
0x180006638  jmp     loc_180006886
0x18000663d  call    DsRolepInitializeOperationHandle
0x180006642  mov     ebx, eax
0x180006644  test    eax, eax
0x180006646  jnz     loc_180006870
0x18000664c  call    cs:__imp_LsaISafeMode
0x180006652  test    al, al
0x180006654  jz      short loc_18000665A
0x180006656  test    esi, esi
0x180006658  jnz     short loc_180006688
0x18000665a  lea     rcx, [rbp+37h+arg_20]
0x18000665e  mov     dword ptr [rbp+37h+arg_20], 0
0x180006665  call    DsRolepGetMachineType
0x18000666a  mov     ebx, eax
0x18000666c  test    eax, eax
0x18000666e  jnz     loc_180006869
0x180006674  mov     edx, dword ptr [rbp+37h+arg_20]
0x180006677  test    edx, edx
0x180006679  jz      loc_180006853
0x18000667f  cmp     edx, 1
0x180006682  jz      loc_180006853
0x180006688  mov     r8b, 1
0x18000668b  lea     rcx, DsRolepDemoteSD; pSecurityDescriptor
0x180006692  call    DsRolepCheckClientAccess
0x180006697  mov     ebx, eax
0x180006699  test    eax, eax
0x18000669b  jnz     loc_180006869
0x1800066a1  mov     rax, [rbp+37h+arg_50]
0x1800066a8  lea     ecx, [rbx+1]
0x1800066ab  mov     qword ptr [rax], 0
0x1800066b2  call    DsRolepInitializeLogHelper
0x1800066b7  lea     rdx, aRequestForDemo_0; "Request for demotion of domain controll"...
0x1800066be  lea     ecx, [rbx+4]
0x1800066c1  call    DsRolepLogPrintRoutine
0x1800066c6  mov     rax, [rbp+37h+arg_8]
0x1800066ca  lea     rbx, aNull; "(NULL)"
0x1800066d1  test    rax, rax
0x1800066d4  lea     rdx, aDnsdomainnameW; "DnsDomainName  %ws\n"
0x1800066db  mov     r8, rax
0x1800066de  mov     ecx, 4
0x1800066e3  cmovz   r8, rbx
0x1800066e7  call    DsRolepLogPrintRoutine
0x1800066ec  mov     r8d, edi
0x1800066ef  lea     rdx, aServerroleLu; "\tServerRole  %lu\n"
0x1800066f6  mov     ecx, 4
0x1800066fb  call    DsRolepLogPrintRoutine
0x180006700  mov     rax, [rbp+37h+arg_18]
0x180006704  lea     rdx, aAccountWs_1; "\tAccount %ws "
0x18000670b  test    rax, rax
0x18000670e  mov     r8, rax
0x180006711  cmovz   r8, rbx
0x180006715  mov     ebx, 4
0x18000671a  mov     ecx, ebx
0x18000671c  call    DsRolepLogPrintRoutine
0x180006721  mov     r8d, r14d
0x180006724  lea     rdx, aOptionsLu; "\tOptions  %lu\n"
0x18000672b  mov     ecx, ebx
0x18000672d  call    DsRolepLogPrintRoutine
0x180006732  cmp     dword ptr [rbp+37h+arg_30], 0
0x180006736  lea     rax, aFalse; "FALSE"
0x18000673d  lea     rbx, aTrue; "TRUE"
0x180006744  mov     ecx, 4
0x180006749  mov     r8, rbx
0x18000674c  lea     rdx, aLastdcindomain; "\tLastDcInDomain  %S\n"
0x180006753  cmovz   r8, rax
0x180006757  call    DsRolepLogPrintRoutine
0x18000675c  test    esi, esi
0x18000675e  lea     rdx, aForcedDemoteS; "\tForced Demote  %S\n"
0x180006765  lea     rsi, aFalse; "FALSE"
0x18000676c  mov     r8, rbx
0x18000676f  cmovz   r8, rsi
0x180006773  mov     ecx, 4
0x180006778  call    DsRolepLogPrintRoutine
0x18000677d  bt      r14d, 13h
0x180006782  lea     rdx, aStage2OnlyS; "\tStage 2 only   %S\n"
0x180006789  cmovnb  rbx, rsi
0x18000678d  mov     esi, 4
0x180006792  mov     ecx, esi
0x180006794  mov     r8, rbx
0x180006797  call    DsRolepLogPrintRoutine
0x18000679c  mov     rcx, [rbp+37h+arg_0]
0x1800067a0  lea     r9, [rbp+37h+var_58]
0x1800067a4  lea     r8d, [rsi-2]
0x1800067a8  mov     qword ptr [rsp+0C0h+var_A0], 0
0x1800067b1  lea     rdx, [rbp+37h+var_68]
0x1800067b5  call    DsRolepDecryptPasswordsWithKey
0x1800067ba  mov     ebx, eax
0x1800067bc  test    eax, eax
0x1800067be  jnz     loc_180006869
0x1800067c4  lea     rdx, aStartTheWorker; "Start the worker task\n"
0x1800067cb  mov     ecx, esi
0x1800067cd  call    DsRolepLogPrintRoutine
0x1800067d2  movzx   eax, byte ptr [rbp+37h+arg_30]
0x1800067d6  lea     rcx, [rbp+37h+var_70]
0x1800067da  mov     r8, [rbp+37h+arg_18]
0x1800067de  lea     r9, [rbp+37h+var_58]
0x1800067e2  mov     rdx, [rbp+37h+arg_8]
0x1800067e6  mov     [rsp+48h], rcx
0x1800067eb  lea     rcx, [rbp+37h+var_48]
0x1800067ef  mov     [rsp+0C0h+var_80], rcx
0x1800067f4  mov     ecx, edi
0x1800067f6  mov     [rsp+0C0h+var_88], r12
0x1800067fb  mov     dword ptr [rsp+0C0h+var_90], r15d
0x180006800  mov     [rsp+0C0h+var_98], eax
0x180006804  mov     [rsp+0C0h+var_A0], r14d
0x180006809  call    DsRolepBuildDemoteArgumentBlock
0x18000680e  lea     edi, [rsi-2]
0x180006811  mov     ebx, eax
0x180006813  mov     edx, edi
0x180006815  lea     rcx, [rbp+37h+var_58]
0x180006819  call    DsRolepFreePasswords
0x18000681e  test    ebx, ebx
0x180006820  jnz     short loc_180006869
0x180006822  mov     rdx, [rbp+37h+var_70]
0x180006826  mov     ecx, edi
0x180006828  call    DsRolepSpinWorkerThread
0x18000682d  mov     ebx, eax
0x18000682f  test    eax, eax
0x180006831  jz      short loc_180006840
0x180006833  xor     edx, edx
0x180006835  lea     rcx, [rbp+37h+var_70]
0x180006839  call    DsRolepFreeArgumentBlock
0x18000683e  jmp     short loc_180006869
0x180006840  mov     rax, [rbp+37h+arg_50]
0x180006847  lea     rcx, DsRolepCurrentOperationHandle
0x18000684e  mov     [rax], rcx
0x180006851  jmp     short loc_180006870
0x180006853  lea     rdx, aThisOperationI; "This operation is only valid on a domai"...
0x18000685a  mov     ecx, 4
0x18000685f  call    DsRolepLogPrintRoutine
0x180006864  mov     ebx, 548h
0x180006869  xor     ecx, ecx
0x18000686b  call    DsRolepResetOperationHandle
0x180006870  mov     r8d, ebx
0x180006873  lea     rdx, aRequestForDemo; "Request for demotion returning %lu\n"
0x18000687a  mov     ecx, 4
0x18000687f  call    DsRolepLogPrintRoutine
0x180006884  mov     eax, ebx
0x180006886  add     rsp, 90h
0x18000688d  pop     r15
0x18000688f  pop     r14
0x180006891  pop     r12
0x180006893  pop     rdi
0x180006894  pop     rsi
0x180006895  pop     rbx
0x180006896  pop     rbp
0x180006897  retn
```
