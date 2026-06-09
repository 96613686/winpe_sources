# DiskFdoExecuteWmiMethod

- ea: `0x140010490`
- end: `0x1400109a7`
- name: `DiskFdoExecuteWmiMethod`
- size: `1303`
- prototype: `NTSTATUS __fastcall(__int64, IRP *, int, int, unsigned int, unsigned int, char *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400035c0`
- `0x140003680`
- `0x140004624`
- `0x140005118`
- `0x1400051e8`
- `0x140005244`
- `0x14000e200`
- `0x14000e31c`
- `0x14001016c`
- `0x140010490`
- `0x140010f3c`
- `0x140011118`
- `0x140014d90`

## import_xrefs

- `CLASSPNP!ClassWmiCompleteRequest` at `0x140010982`
- `CLASSPNP!ClassWmiCompleteRequest` at `0x140010982`

## pseudocode

```c
NTSTATUS __fastcall DiskFdoExecuteWmiMethod(
        __int64 a1,
        IRP *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        char *a7)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *v7; // r13
  IRP *v9; // r8
  __int64 v11; // rdx
  _DWORD *DriverData; // r15
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  NTSTATUS InfoExceptionInformation; // ebx
  ULONG v18; // ebp
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // eax
  int v27; // ebx
  int SmartLog; // eax
  __int64 v29; // r9
  int v30; // edi
  unsigned int v31; // esi
  __int64 v32; // rdx
  unsigned int v33; // edi
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  bool v36; // zf
  IRP *v37; // rsi
  struct _DEVICE_OBJECT *v38; // rdi
  __int64 v40; // [rsp+50h] [rbp-48h] BYREF
  int v41; // [rsp+58h] [rbp-40h]

  v7 = *(struct _FUNCTIONAL_DEVICE_EXTENSION **)(a1 + 64);
  v9 = a2;
  v11 = a1;
  DriverData = v7->CommonExtension.DriverData;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqddDDq(WPP_GLOBAL_Control->AttachedDevice, a1, v9, a1, v9, a3, a4, a5, a6, a7);
  }
  if ( !a3 )
    goto LABEL_83;
  v13 = a3 - 1;
  if ( !v13 )
    goto LABEL_83;
  v14 = v13 - 1;
  if ( !v14 )
    goto LABEL_83;
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 && (unsigned int)(v16 - 1) >= 2 )
    {
      InfoExceptionInformation = -1073741163;
LABEL_84:
      v18 = 0;
      goto LABEL_85;
    }
LABEL_83:
    InfoExceptionInformation = -1073741808;
    goto LABEL_84;
  }
  v18 = 0;
  v19 = a4 - 1;
  if ( !v19 )
  {
    if ( !a5 )
      goto LABEL_30;
    v33 = (unsigned __int8)*a7;
    InfoExceptionInformation = 0;
    if ( *((_BYTE *)DriverData + 20) != (_BYTE)v33 )
    {
      v36 = DriverData[4] == 3;
      *((_BYTE *)DriverData + 20) = v33;
      if ( v36 )
      {
        v40 = 0;
        v41 = 0;
        InfoExceptionInformation = DiskGetInfoExceptionInformation((__int64)v7, (__int64)&v40);
        if ( InfoExceptionInformation >= 0 )
        {
          BYTE2(v40) = BYTE2(v40) & 0x7F | ((_BYTE)v33 == 0 ? 0x80 : 0);
          InfoExceptionInformation = DiskSetInfoExceptionInformation((__int64)v7, &v40);
        }
      }
      else
      {
        InfoExceptionInformation = -1073741808;
      }
    }
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_89;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      goto LABEL_85;
    v35 = 45;
    goto LABEL_72;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    if ( !a5 )
      goto LABEL_30;
    v33 = (unsigned __int8)*a7;
    if ( !(_BYTE)v33 )
      DiskEnableDisableFailurePredictPolling(v7);
    LOBYTE(v11) = v33;
    InfoExceptionInformation = DiskEnableDisableFailurePrediction(v7, v11, v9);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_89;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      goto LABEL_85;
    v35 = 46;
LABEL_72:
    WPP_SF_DqL(v34->AttachedDevice, v35, v9, v33, v7->DeviceObject, InfoExceptionInformation);
    goto LABEL_85;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    if ( a5 < 5 )
      goto LABEL_30;
    v30 = *(_DWORD *)a7;
    v31 = (unsigned __int8)a7[4];
    InfoExceptionInformation = DiskEnableDisableFailurePredictPolling(v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DDqL(WPP_GLOBAL_Control->AttachedDevice, v32, v9, v31, v30, v7->DeviceObject, InfoExceptionInformation);
      goto LABEL_85;
    }
LABEL_89:
    v38 = (struct _DEVICE_OBJECT *)a1;
    v37 = a2;
    return ClassWmiCompleteRequest(v38, v37, InfoExceptionInformation, v18, 0);
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v18 = 4;
    if ( a6 < 4 )
      goto LABEL_29;
    v29 = (unsigned int)DriverData[4];
    InfoExceptionInformation = 0;
    *(_DWORD *)a7 = v29;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DqL(WPP_GLOBAL_Control->AttachedDevice, 48, v9, v29, v7->DeviceObject, 0);
      goto LABEL_85;
    }
    goto LABEL_89;
  }
  v23 = v22 - 1;
  if ( v23 )
  {
    v24 = v23 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 != 1 )
        {
          InfoExceptionInformation = -1073741161;
          goto LABEL_85;
        }
        if ( DriverData[4] == 2 )
        {
          if ( a5 )
          {
            v18 = 4;
            if ( a6 >= 4 )
            {
              if ( (unsigned __int8)*a7 < 3u )
              {
                LOBYTE(v11) = *a7;
                InfoExceptionInformation = DiskExecuteSmartDiagnostics(v7, v11, v9);
                if ( InfoExceptionInformation < 0 )
                {
                  *(_DWORD *)a7 = 2;
                  InfoExceptionInformation = 0;
                }
                else
                {
                  *(_DWORD *)a7 = 0;
                }
              }
              else
              {
                *(_DWORD *)a7 = 1;
                InfoExceptionInformation = 0;
              }
              goto LABEL_85;
            }
LABEL_29:
            InfoExceptionInformation = -1073741789;
            goto LABEL_85;
          }
LABEL_30:
          InfoExceptionInformation = -1073741811;
          goto LABEL_85;
        }
LABEL_31:
        InfoExceptionInformation = -1073741808;
        goto LABEL_85;
      }
      if ( DriverData[4] != 2 )
        goto LABEL_31;
      if ( (int)a5 < 8 || a5 < ((unsigned __int8)a7[1] << 9) + 8 )
        goto LABEL_30;
      v18 = 1;
      if ( !a6 )
        goto LABEL_29;
      v26 = DiskWriteSmartLog((__int64)v7, a7[1], *a7, a7 + 8);
      InfoExceptionInformation = 0;
      if ( v26 >= 0 )
        InfoExceptionInformation = v26;
      *a7 = v26 >= 0;
    }
    else
    {
      if ( DriverData[4] != 2 )
        goto LABEL_31;
      if ( a5 < 2 )
        goto LABEL_30;
      v27 = (unsigned __int8)a7[1] << 9;
      v18 = v27 + 4;
      if ( a6 < v27 + 4 )
        goto LABEL_29;
      SmartLog = DiskReadSmartLog((__int64)v7, a7[1], *a7, a7 + 4);
      if ( SmartLog < 0 )
        v27 = 0;
      *(_DWORD *)a7 = v27;
      InfoExceptionInformation = 0;
      if ( SmartLog >= 0 )
        InfoExceptionInformation = SmartLog;
    }
  }
  else
  {
    v18 = 1;
    if ( !a6 )
      goto LABEL_29;
    if ( DriverData[4] == 2 )
      InfoExceptionInformation = DiskExecuteSmartDiagnostics(v7, 0, v9);
    else
      InfoExceptionInformation = -1073741808;
    *a7 = InfoExceptionInformation >= 0;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_89;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qL(WPP_GLOBAL_Control->AttachedDevice, v11, v9, v7->DeviceObject, InfoExceptionInformation);
  }
LABEL_85:
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
    goto LABEL_89;
  v37 = a2;
  v38 = (struct _DEVICE_OBJECT *)a1;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 50, v9, a1, a2, InfoExceptionInformation);
  return ClassWmiCompleteRequest(v38, v37, InfoExceptionInformation, v18, 0);
}

```

## disassembly

```asm
0x140010490  mov     r11, rsp
0x140010493  mov     [r11+18h], rbx
0x140010497  mov     [r11+10h], rdx
0x14001049b  mov     [r11+8], rcx
0x14001049f  push    rbp
0x1400104a0  push    rsi
0x1400104a1  push    rdi
0x1400104a2  push    r12
0x1400104a4  push    r13
0x1400104a6  push    r14
0x1400104a8  push    r15
0x1400104aa  sub     rsp, 60h
0x1400104ae  mov     r13, [rcx+40h]
0x1400104b2  mov     ebx, r8d
0x1400104b5  mov     r8, rdx
0x1400104b8  mov     edi, r9d
0x1400104bb  mov     rdx, rcx
0x1400104be  mov     r15, [r13+60h]
0x1400104c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104c9  lea     rax, WPP_GLOBAL_Control
0x1400104d0  mov     rsi, [rsp+98h+arg_30]
0x1400104d8  mov     r12d, [rsp+98h+arg_28]
0x1400104e0  mov     r14d, [rsp+98h+arg_20]
0x1400104e8  cmp     rcx, rax
0x1400104eb  jz      short loc_140010526
0x1400104ed  mov     eax, [rcx+2Ch]
0x1400104f0  test    al, 40h
0x1400104f2  jz      short loc_14001051F
0x1400104f4  cmp     byte ptr [rcx+29h], 4
0x1400104f8  jb      short loc_14001051F
0x1400104fa  mov     rcx, [rcx+18h]
0x1400104fe  mov     [r11-50h], rsi
0x140010502  mov     [r11-58h], r12d
0x140010506  mov     [r11-60h], r14d
0x14001050a  mov     [rsp+98h+var_68], r9d
0x14001050f  mov     r9, rdx
0x140010512  mov     dword ptr [rsp+98h+var_70], ebx
0x140010516  mov     [r11-78h], r8
0x14001051a  call    WPP_SF_qqddDDq
0x14001051f  lea     rax, WPP_GLOBAL_Control
0x140010526  test    ebx, ebx
0x140010528  jz      loc_14001090E
0x14001052e  sub     ebx, 1
0x140010531  jz      loc_14001090E
0x140010537  sub     ebx, 1
0x14001053a  jz      loc_14001090E
0x140010540  sub     ebx, 1
0x140010543  jz      short loc_14001056A
0x140010545  sub     ebx, 1
0x140010548  jz      loc_14001090E
0x14001054e  sub     ebx, 1
0x140010551  jz      loc_14001090E
0x140010557  cmp     ebx, 1
0x14001055a  jz      loc_14001090E
0x140010560  mov     ebx, 0C0000295h
0x140010565  jmp     loc_140010913
0x14001056a  xor     ebp, ebp
0x14001056c  sub     edi, 1
0x14001056f  jz      loc_140010878
0x140010575  sub     edi, 1
0x140010578  jz      loc_1400107FD
0x14001057e  sub     edi, 1
0x140010581  jz      loc_14001078F
0x140010587  sub     edi, 1
0x14001058a  jz      loc_140010735
0x140010590  sub     edi, 1
0x140010593  jz      loc_1400106C1
0x140010599  sub     edi, 1
0x14001059c  jz      loc_14001067B
0x1400105a2  sub     edi, 1
0x1400105a5  jz      loc_140010630
0x1400105ab  cmp     edi, 1
0x1400105ae  jz      short loc_1400105BA
0x1400105b0  mov     ebx, 0C0000297h
0x1400105b5  jmp     loc_140010915
0x1400105ba  cmp     dword ptr [r15+10h], 2
0x1400105bf  jnz     short loc_140010626
0x1400105c1  cmp     r14d, 1
0x1400105c5  jb      short loc_14001061C
0x1400105c7  mov     ebp, 4
0x1400105cc  cmp     r12d, ebp
0x1400105cf  jb      short loc_140010612
0x1400105d1  mov     dl, [rsi]
0x1400105d3  cmp     dl, 3
0x1400105d6  jb      short loc_1400105E5
0x1400105d8  mov     dword ptr [rsi], 1
0x1400105de  xor     ebx, ebx
0x1400105e0  jmp     loc_140010915
0x1400105e5  mov     rcx, r13
0x1400105e8  call    DiskExecuteSmartDiagnostics
0x1400105ed  lea     r14, WPP_GLOBAL_Control
0x1400105f4  mov     ebx, eax
0x1400105f6  test    eax, eax
0x1400105f8  js      short loc_140010605
0x1400105fa  mov     dword ptr [rsi], 0
0x140010600  jmp     loc_14001091C
0x140010605  mov     dword ptr [rsi], 2
0x14001060b  xor     ebx, ebx
0x14001060d  jmp     loc_14001091C
0x140010612  mov     ebx, 0C0000023h
0x140010617  jmp     loc_140010915
0x14001061c  mov     ebx, 0C000000Dh
0x140010621  jmp     loc_140010915
0x140010626  mov     ebx, 0C0000010h
0x14001062b  jmp     loc_140010915
0x140010630  cmp     dword ptr [r15+10h], 2
0x140010635  jnz     short loc_140010626
0x140010637  cmp     r14d, 8
0x14001063b  jl      short loc_14001061C
0x14001063d  movzx   edx, byte ptr [rsi+1]
0x140010641  mov     eax, edx
0x140010643  shl     eax, 9
0x140010646  add     eax, 8
0x140010649  cmp     r14d, eax
0x14001064c  jb      short loc_14001061C
0x14001064e  mov     ebp, 1
0x140010653  cmp     r12d, ebp
0x140010656  jb      short loc_140010612
0x140010658  mov     r8b, [rsi]
0x14001065b  lea     r9, [rsi+8]
0x14001065f  mov     rcx, r13; int
0x140010662  call    DiskWriteSmartLog
0x140010667  xor     ebx, ebx
0x140010669  test    eax, eax
0x14001066b  cmovns  ebx, eax
0x14001066e  shr     eax, 1Fh
0x140010671  xor     al, bpl
0x140010674  mov     [rsi], al
0x140010676  jmp     loc_140010915
0x14001067b  cmp     dword ptr [r15+10h], 2
0x140010680  jnz     short loc_140010626
0x140010682  cmp     r14d, 2
0x140010686  jb      short loc_14001061C
0x140010688  movzx   edx, byte ptr [rsi+1]
0x14001068c  mov     ebx, edx
0x14001068e  shl     ebx, 9
0x140010691  lea     ebp, [rbx+4]
0x140010694  cmp     r12d, ebp
0x140010697  jb      loc_140010612
0x14001069d  mov     r8b, [rsi]
0x1400106a0  lea     r9, [rsi+4]
0x1400106a4  mov     rcx, r13; int
0x1400106a7  call    DiskReadSmartLog
0x1400106ac  xor     ecx, ecx
0x1400106ae  test    eax, eax
0x1400106b0  cmovs   ebx, ecx
0x1400106b3  mov     [rsi], ebx
0x1400106b5  xor     ebx, ebx
0x1400106b7  test    eax, eax
0x1400106b9  cmovns  ebx, eax
0x1400106bc  jmp     loc_140010915
0x1400106c1  mov     ebp, 1
0x1400106c6  cmp     r12d, ebp
0x1400106c9  jb      loc_140010612
0x1400106cf  cmp     dword ptr [r15+10h], 2
0x1400106d4  jnz     short loc_1400106E4
0x1400106d6  xor     edx, edx
0x1400106d8  mov     rcx, r13
0x1400106db  call    DiskExecuteSmartDiagnostics
0x1400106e0  mov     ebx, eax
0x1400106e2  jmp     short loc_1400106E9
0x1400106e4  mov     ebx, 0C0000010h
0x1400106e9  mov     eax, ebx
0x1400106eb  shr     eax, 1Fh
0x1400106ee  xor     al, bpl
0x1400106f1  mov     [rsi], al
0x1400106f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106fa  lea     r14, WPP_GLOBAL_Control
0x140010701  cmp     rcx, r14
0x140010704  jz      loc_140010961
0x14001070a  mov     eax, [rcx+2Ch]
0x14001070d  test    al, 40h
0x14001070f  jz      loc_14001091C
0x140010715  cmp     byte ptr [rcx+29h], 4
0x140010719  jb      loc_14001091C
0x14001071f  mov     r9, [r13+8]
0x140010723  mov     rcx, [rcx+18h]
0x140010727  mov     dword ptr [rsp+98h+PriorityBoost], ebx
0x14001072b  call    WPP_SF_qL
0x140010730  jmp     loc_14001091C
0x140010735  mov     ebp, 4
0x14001073a  cmp     r12d, ebp
0x14001073d  jb      loc_140010612
0x140010743  mov     r9d, [r15+10h]
0x140010747  xor     ebx, ebx
0x140010749  mov     [rsi], r9d
0x14001074c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010753  cmp     rcx, rax
0x140010756  jz      loc_140010961
0x14001075c  mov     eax, [rcx+2Ch]
0x14001075f  test    al, 40h
0x140010761  jz      loc_140010915
0x140010767  cmp     [rcx+29h], bpl
0x14001076b  jb      loc_140010915
0x140010771  mov     rax, [r13+8]
0x140010775  lea     edx, [rbp+2Ch]
0x140010778  mov     rcx, [rcx+18h]
0x14001077c  mov     dword ptr [rsp+98h+var_70], ebx
0x140010780  mov     qword ptr [rsp+98h+PriorityBoost], rax
0x140010785  call    WPP_SF_DqL
0x14001078a  jmp     loc_140010915
0x14001078f  cmp     r14d, 5
0x140010793  jb      loc_14001061C
0x140010799  mov     edi, [rsi]
0x14001079b  mov     rcx, r13; FdoExtension
0x14001079e  movzx   esi, byte ptr [rsi+4]
0x1400107a2  mov     r8d, edi
0x1400107a5  mov     dl, sil
0x1400107a8  call    DiskEnableDisableFailurePredictPolling
0x1400107ad  mov     ebx, eax
0x1400107af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107b6  lea     r14, WPP_GLOBAL_Control
0x1400107bd  cmp     rcx, r14
0x1400107c0  jz      loc_140010961
0x1400107c6  mov     eax, [rcx+2Ch]
0x1400107c9  test    al, 40h
0x1400107cb  jz      loc_14001091C
0x1400107d1  cmp     byte ptr [rcx+29h], 4
0x1400107d5  jb      loc_14001091C
0x1400107db  mov     rax, [r13+8]
0x1400107df  mov     r9d, esi
0x1400107e2  mov     rcx, [rcx+18h]
0x1400107e6  mov     [rsp+98h+var_68], ebx
0x1400107ea  mov     [rsp+98h+var_70], rax
0x1400107ef  mov     dword ptr [rsp+98h+PriorityBoost], edi
0x1400107f3  call    WPP_SF_DDqL
0x1400107f8  jmp     loc_14001091C
0x1400107fd  cmp     r14d, 1
0x140010801  jb      loc_14001061C
0x140010807  movzx   edi, byte ptr [rsi]
0x14001080a  test    dil, dil
0x14001080d  jnz     short loc_14001081C
0x14001080f  xor     r8d, r8d
0x140010812  xor     edx, edx
0x140010814  mov     rcx, r13; FdoExtension
0x140010817  call    DiskEnableDisableFailurePredictPolling
0x14001081c  mov     dl, dil
0x14001081f  mov     rcx, r13
0x140010822  call    DiskEnableDisableFailurePrediction
0x140010827  mov     ebx, eax
0x140010829  mov     rcx, cs:WPP_GLOBAL_Control
0x140010830  lea     r14, WPP_GLOBAL_Control
0x140010837  cmp     rcx, r14
0x14001083a  jz      loc_140010961
0x140010840  mov     eax, [rcx+2Ch]
0x140010843  test    al, 40h
0x140010845  jz      loc_14001091C
0x14001084b  cmp     byte ptr [rcx+29h], 4
0x14001084f  jb      loc_14001091C
0x140010855  mov     edx, 2Eh ; '.'
0x14001085a  mov     rax, [r13+8]
0x14001085e  mov     r9d, edi
0x140010861  mov     rcx, [rcx+18h]
0x140010865  mov     dword ptr [rsp+98h+var_70], ebx
0x140010869  mov     qword ptr [rsp+98h+PriorityBoost], rax
0x14001086e  call    WPP_SF_DqL
0x140010873  jmp     loc_14001091C
0x140010878  cmp     r14d, 1
0x14001087c  jb      loc_14001061C
0x140010882  movzx   edi, byte ptr [rsi]
0x140010885  xor     ebx, ebx
0x140010887  cmp     [r15+14h], dil
0x14001088b  jz      short loc_1400108E4
0x14001088d  cmp     dword ptr [r15+10h], 3
0x140010892  mov     [r15+14h], dil
0x140010896  jnz     short loc_1400108DF
0x140010898  xor     eax, eax
0x14001089a  lea     rdx, [rsp+98h+var_48]
0x14001089f  mov     rcx, r13
0x1400108a2  mov     [rsp+98h+var_48], rax
0x1400108a7  mov     [rsp+98h+var_40], eax
0x1400108ab  call    DiskGetInfoExceptionInformation
0x1400108b0  mov     ebx, eax
0x1400108b2  test    eax, eax
0x1400108b4  js      short loc_1400108E4
0x1400108b6  mov     al, dil
0x1400108b9  lea     rdx, [rsp+98h+var_48]
0x1400108be  neg     al
0x1400108c0  mov     al, byte ptr [rsp+98h+var_48+2]
0x1400108c4  sbb     cl, cl
0x1400108c6  and     al, 7Fh
0x1400108c8  not     cl
0x1400108ca  and     cl, 80h
0x1400108cd  or      cl, al
0x1400108cf  mov     byte ptr [rsp+98h+var_48+2], cl
0x1400108d3  mov     rcx, r13
0x1400108d6  call    DiskSetInfoExceptionInformation
0x1400108db  mov     ebx, eax
0x1400108dd  jmp     short loc_1400108E4
0x1400108df  mov     ebx, 0C0000010h
0x1400108e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400108eb  lea     r14, WPP_GLOBAL_Control
0x1400108f2  cmp     rcx, r14
0x1400108f5  jz      short loc_140010961
0x1400108f7  mov     eax, [rcx+2Ch]
0x1400108fa  test    al, 40h
0x1400108fc  jz      short loc_14001091C
0x1400108fe  cmp     byte ptr [rcx+29h], 4
0x140010902  jb      short loc_14001091C
0x140010904  mov     edx, 2Dh ; '-'
  ... truncated ...
```
