# IsHotPlugDevice(ulong)

- ea: `0x180006190`
- end: `0x180006332`
- name: `?IsHotPlugDevice@@YAHK@Z`
- size: `418`
- prototype: `__int64 __fastcall(DEVINST)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003a14`
- `0x180004664`
- `0x180006190`

## callees

- `0x180006190`

## import_xrefs

- `CFGMGR32!CM_Get_Parent_Ex` at `0x1800062fc`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x1800062fc`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000621d`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800062b7`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000621d`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800062b7`
- `CFGMGR32!CM_Get_DevNode_Status_Ex` at `0x1800061df`
- `CFGMGR32!CM_Get_DevNode_Status_Ex` at `0x1800061df`

## pseudocode

```c
__int64 __fastcall IsHotPlugDevice(DEVINST a1)
{
  unsigned int v2; // esi
  ULONG v3; // ebx
  char v4; // di
  char v5; // r14
  int v6; // edi
  int v7; // r14d
  unsigned int v8; // ebx
  int v9; // r15d
  ULONG pulStatus; // [rsp+40h] [rbp-20h] BYREF
  int v12; // [rsp+44h] [rbp-1Ch] BYREF
  DEVINST dnDevInst; // [rsp+48h] [rbp-18h] BYREF
  ULONG pulProblemNumber; // [rsp+4Ch] [rbp-14h] BYREF
  ULONG ulProperty[4]; // [rsp+50h] [rbp-10h]
  ULONG pulLength; // [rsp+A8h] [rbp+48h] BYREF
  ULONG pulRegDataType; // [rsp+B0h] [rbp+50h] BYREF
  int Buffer; // [rsp+B8h] [rbp+58h] BYREF

  pulRegDataType = 0;
  pulLength = 0;
  Buffer = 0;
  pulStatus = 0;
  v2 = 0;
  pulProblemNumber = 0;
  v12 = 0;
  dnDevInst = 0;
  if ( !CM_Get_DevNode_Status_Ex(&pulStatus, &pulProblemNumber, a1, 0, 0) )
  {
    pulLength = 4;
    v3 = pulStatus & 8;
    if ( CM_Get_DevNode_Registry_Property_ExW(a1, 0x10u, &pulRegDataType, &Buffer, &pulLength, 0, 0)
      || pulRegDataType != 4
      || pulLength < 4 )
    {
      v4 = 0;
      Buffer = 0;
    }
    else
    {
      v4 = Buffer;
    }
    if ( (v4 & 8) == 0 && (v3 || (v4 & 2) != 0) )
    {
      v5 = v4;
      v6 = v4 & 0x80;
      v7 = v5 & 4;
      if ( v7 && !v6 )
        return 1;
      ulProperty[0] = 34;
      v9 = 0;
      ulProperty[1] = 33;
      v8 = 1;
      ulProperty[2] = 32;
      while ( 1 )
      {
        pulLength = 4;
        if ( !CM_Get_DevNode_Registry_Property_ExW(a1, ulProperty[v9], &pulRegDataType, &v12, &pulLength, 0, 0)
          && pulRegDataType == 4
          && pulLength >= 4
          && v12 != 1
          && !v6 )
        {
          break;
        }
        if ( (unsigned int)++v9 >= 3 )
        {
          v8 = 0;
          break;
        }
      }
      if ( v7 )
        return v8;
      if ( v8 && !CM_Get_Parent_Ex(&dnDevInst, a1, 0, 0) && dnDevInst )
        LOBYTE(v2) = (unsigned int)IsHotPlugDevice(dnDevInst) == 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180006190  mov     [rsp-38h+arg_0], rbx
0x180006195  push    rbp
0x180006196  push    rsi
0x180006197  push    rdi
0x180006198  push    r12
0x18000619a  push    r13
0x18000619c  push    r14
0x18000619e  push    r15
0x1800061a0  mov     rbp, rsp
0x1800061a3  sub     rsp, 60h
0x1800061a7  xor     r13d, r13d
0x1800061aa  lea     rdx, [rbp+pulProblemNumber]; pulProblemNumber
0x1800061ae  mov     r12d, ecx
0x1800061b1  mov     [rbp+pulRegDataType], r13d
0x1800061b5  mov     r8d, ecx; dnDevInst
0x1800061b8  mov     [rbp+pulLength], r13d
0x1800061bc  lea     rcx, [rbp+pulStatus]; pulStatus
0x1800061c0  mov     [rbp+Buffer], r13d
0x1800061c4  xor     r9d, r9d; ulFlags
0x1800061c7  mov     [rbp+pulStatus], r13d
0x1800061cb  mov     esi, r13d
0x1800061ce  mov     [rbp+pulProblemNumber], r13d
0x1800061d2  mov     [rbp+var_1C], r13d
0x1800061d6  mov     [rbp+dnDevInst], r13d
0x1800061da  mov     [rsp+60h+hMachine], r13; hMachine
0x1800061df  call    cs:__imp_CM_Get_DevNode_Status_Ex
0x1800061e5  test    eax, eax
0x1800061e7  jnz     loc_180006318
0x1800061ed  mov     ebx, [rbp+pulStatus]
0x1800061f0  lea     rax, [rbp+pulLength]
0x1800061f4  mov     [rsp+60h+var_30], r13; hMachine
0x1800061f9  lea     r15d, [r13+4]
0x1800061fd  mov     [rsp+60h+ulFlags], r13d; ulFlags
0x180006202  lea     r9, [rbp+Buffer]; Buffer
0x180006206  lea     r8, [rbp+pulRegDataType]; pulRegDataType
0x18000620a  mov     [rbp+pulLength], r15d
0x18000620e  lea     edx, [r13+10h]; ulProperty
0x180006212  mov     [rsp+60h+hMachine], rax; pulLength
0x180006217  mov     ecx, r12d; dnDevInst
0x18000621a  and     ebx, 8
0x18000621d  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180006223  test    eax, eax
0x180006225  jnz     short loc_180006238
0x180006227  cmp     [rbp+pulRegDataType], r15d
0x18000622b  jnz     short loc_180006238
0x18000622d  cmp     [rbp+pulLength], r15d
0x180006231  jb      short loc_180006238
0x180006233  mov     edi, [rbp+Buffer]
0x180006236  jmp     short loc_18000623F
0x180006238  mov     edi, r13d
0x18000623b  mov     [rbp+Buffer], r13d
0x18000623f  test    dil, 8
0x180006243  jnz     loc_180006318
0x180006249  test    ebx, ebx
0x18000624b  jnz     short loc_180006257
0x18000624d  test    dil, 2
0x180006251  jz      loc_180006318
0x180006257  mov     r14d, edi
0x18000625a  and     edi, 80h
0x180006260  and     r14d, r15d
0x180006263  jz      short loc_18000626E
0x180006265  test    edi, edi
0x180006267  jnz     short loc_18000626E
0x180006269  lea     ebx, [rdi+1]
0x18000626c  jmp     short loc_1800062E7
0x18000626e  mov     [rbp+ulProperty], 22h ; '"'
0x180006275  mov     r15d, r13d
0x180006278  mov     [rbp+var_C], 21h ; '!'
0x18000627f  mov     ebx, 1
0x180006284  mov     [rbp+var_8], 20h ; ' '
0x18000628b  mov     edx, r15d
0x18000628e  lea     rax, [rbp+pulLength]
0x180006292  mov     [rsp+60h+var_30], r13; hMachine
0x180006297  lea     r9, [rbp+var_1C]; Buffer
0x18000629b  mov     [rsp+60h+ulFlags], r13d; ulFlags
0x1800062a0  lea     r8, [rbp+pulRegDataType]; pulRegDataType
0x1800062a4  mov     ecx, r12d; dnDevInst
0x1800062a7  mov     [rbp+pulLength], 4
0x1800062ae  mov     edx, [rbp+rdx*4+ulProperty]; ulProperty
0x1800062b2  mov     [rsp+60h+hMachine], rax; pulLength
0x1800062b7  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x1800062bd  test    eax, eax
0x1800062bf  jnz     short loc_1800062D6
0x1800062c1  cmp     [rbp+pulRegDataType], 4
0x1800062c5  jnz     short loc_1800062D6
0x1800062c7  cmp     [rbp+pulLength], 4
0x1800062cb  jb      short loc_1800062D6
0x1800062cd  cmp     [rbp+var_1C], ebx
0x1800062d0  jz      short loc_1800062D6
0x1800062d2  test    edi, edi
0x1800062d4  jz      short loc_1800062E2
0x1800062d6  add     r15d, ebx
0x1800062d9  cmp     r15d, 3
0x1800062dd  jb      short loc_18000628B
0x1800062df  mov     ebx, r13d
0x1800062e2  test    r14d, r14d
0x1800062e5  jz      short loc_1800062EB
0x1800062e7  mov     esi, ebx
0x1800062e9  jmp     short loc_180006318
0x1800062eb  test    ebx, ebx
0x1800062ed  jz      short loc_180006318
0x1800062ef  xor     r9d, r9d; hMachine
0x1800062f2  lea     rcx, [rbp+dnDevInst]; pdnDevInst
0x1800062f6  xor     r8d, r8d; ulFlags
0x1800062f9  mov     edx, r12d; dnDevInst
0x1800062fc  call    cs:__imp_CM_Get_Parent_Ex
0x180006302  test    eax, eax
0x180006304  jnz     short loc_180006318
0x180006306  mov     ecx, [rbp+dnDevInst]; unsigned int
0x180006309  test    ecx, ecx
0x18000630b  jz      short loc_180006318
0x18000630d  call    ?IsHotPlugDevice@@YAHK@Z; IsHotPlugDevice(ulong)
0x180006312  test    eax, eax
0x180006314  setz    sil
0x180006318  mov     rbx, [rsp+60h+arg_0]
0x180006320  mov     eax, esi
0x180006322  add     rsp, 60h
0x180006326  pop     r15
0x180006328  pop     r14
0x18000632a  pop     r13
0x18000632c  pop     r12
0x18000632e  pop     rdi
0x18000632f  pop     rsi
0x180006330  pop     rbp
0x180006331  retn
```
