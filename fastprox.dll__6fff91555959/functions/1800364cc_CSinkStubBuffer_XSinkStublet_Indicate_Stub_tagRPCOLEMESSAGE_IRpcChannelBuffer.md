# CSinkStubBuffer::XSinkStublet::Indicate_Stub(tagRPCOLEMESSAGE *,IRpcChannelBuffer *)

- ea: `0x1800364cc`
- end: `0x180036833`
- name: `?Indicate_Stub@XSinkStublet@CSinkStubBuffer@@AEAAJPEAUtagRPCOLEMESSAGE@@PEAUIRpcChannelBuffer@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(CSinkStubBuffer::XSinkStublet *__hidden this, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180036480`

## callees

- `0x180035b08`
- `0x1800364cc`
- `0x18003683c`
- `0x180037120`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003675b`
- `wbemcomn!GetMemLogObject` at `0x180036776`
- `wbemcomn!GetMemLogObject` at `0x18003678c`
- `wbemcomn!GetMemLogObject` at `0x1800367c9`
- `wbemcomn!GetMemLogObject` at `0x18003675b`
- `wbemcomn!GetMemLogObject` at `0x180036776`
- `wbemcomn!GetMemLogObject` at `0x18003678c`
- `wbemcomn!GetMemLogObject` at `0x1800367c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036766`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036781`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036797`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800367d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036766`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036781`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036797`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800367d7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800365e9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800365e9`

## pseudocode

```c
__int64 __fastcall CSinkStubBuffer::XSinkStublet::Indicate_Stub(
        CSinkStubBuffer::XSinkStublet *this,
        struct tagRPCOLEMESSAGE *a2,
        struct IRpcChannelBuffer *a3)
{
  char *Buffer; // r9
  ULONG cbBuffer; // eax
  signed int v8; // ebx
  int v9; // r12d
  __int64 v10; // rcx
  struct IWbemClassObject **v11; // r13
  struct IRpcChannelBuffer *v12; // rcx
  int v13; // ebx
  CWbemRefreshingSvc *v14; // rcx
  _DWORD *v16; // rax
  __int64 v17; // rdx
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *MemLogObject; // rax
  char *v22; // [rsp+20h] [rbp-20h] BYREF
  ULONG v23; // [rsp+28h] [rbp-18h]
  char *v24; // [rsp+30h] [rbp-10h]
  int pExceptionObject; // [rsp+88h] [rbp+48h] BYREF
  struct IRpcChannelBuffer *v26; // [rsp+90h] [rbp+50h]
  struct IWbemClassObject **v27; // [rsp+98h] [rbp+58h] BYREF

  v26 = a3;
  Buffer = (char *)a2->Buffer;
  if ( Buffer )
  {
    if ( Buffer + 26 < Buffer )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_7c35078de6b730c8b6b4841e12630b85_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    v24 = Buffer + 26;
  }
  else
  {
    v24 = 0;
  }
  cbBuffer = a2->cbBuffer;
  v8 = -2147217386;
  v23 = cbBuffer;
  v22 = Buffer;
  if ( !Buffer )
    goto LABEL_46;
  if ( cbBuffer < 0x1A )
  {
    v8 = -2147217348;
LABEL_46:
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v8);
    goto LABEL_22;
  }
  if ( ((*(_DWORD *)Buffer + 1) & 0xFFFFFFFE) != 0
    || *(unsigned __int8 near **)(Buffer + 4) != CWbemDataPacket::s_abSignature )
  {
    v8 = -2147217343;
  }
  else if ( (unsigned __int8)Buffer[25] >= 4u )
  {
    v8 = -2147217345;
  }
  else
  {
    v8 = (unsigned __int8)Buffer[24] > 1u ? 0x80041040 : 0;
  }
  if ( v8 == -2147217343 )
    goto LABEL_12;
  if ( v8 < 0 )
    goto LABEL_46;
LABEL_22:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_172c0f1e86c2386173baa66c351dfc86_Traceguids, (unsigned int)v8);
  }
LABEL_12:
  if ( !v8 )
  {
    *((_BYTE *)this + 104) = 0;
    pExceptionObject = 0;
    v27 = 0;
    v9 = CWbemObjSinkIndicatePacket::UnmarshalPacket(
           (CWbemObjSinkIndicatePacket *)&v22,
           &pExceptionObject,
           &v27,
           (CSinkStubBuffer::XSinkStublet *)((char *)this + 40));
    if ( v9 >= 0 )
    {
      v10 = *((_QWORD *)this + 4);
      v11 = v27;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v10 + 24LL))(
             v10,
             (unsigned int)pExceptionObject,
             v27);
      if ( pExceptionObject > 0 )
      {
        do
        {
          ((void (__fastcall *)(struct IWbemClassObject *))v11[v8]->lpVtbl->Release)(v11[v8]);
          ++v8;
        }
        while ( v8 < pExceptionObject );
      }
      CWin32DefaultArena::WbemMemFree(v11);
    }
    v12 = v26;
    a2->cbBuffer = 4;
    v13 = ((__int64 (__fastcall *)(struct IRpcChannelBuffer *, struct tagRPCOLEMESSAGE *, GUID *))v12->lpVtbl->GetBuffer)(
            v12,
            a2,
            &IID_IWbemObjectSink);
    if ( v13 < 0 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, v13);
    }
    else
    {
      *(_DWORD *)a2->Buffer = v9;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v13;
    }
    v17 = 32;
    goto LABEL_43;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *))(**(_QWORD **)(*((_QWORD *)this + 1) + 32LL)
                                                                                                 + 40LL))(
          *(_QWORD *)(*((_QWORD *)this + 1) + 32LL),
          a2,
          a3);
  if ( v13 )
  {
    if ( v13 < 0 )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, v13);
    }
    goto LABEL_39;
  }
  if ( !*((_BYTE *)this + 104) || (v16 = a2->Buffer, *v16) )
  {
LABEL_39:
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v13;
    }
    v17 = 31;
LABEL_43:
    WPP_SF_d(*((_QWORD *)v14 + 2), v17, WPP_370c3275099832fea2075eaa2fb282a8_Traceguids, (unsigned int)v13);
    return (unsigned int)v13;
  }
  *v16 = 262399;
  *((_BYTE *)this + 104) = 0;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_370c3275099832fea2075eaa2fb282a8_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800364cc  mov     [rsp-38h+arg_10], r8
0x1800364d1  push    rbp
0x1800364d2  push    rbx
0x1800364d3  push    rdi
0x1800364d4  push    r12
0x1800364d6  push    r13
0x1800364d8  push    r14
0x1800364da  push    r15
0x1800364dc  mov     rbp, rsp
0x1800364df  sub     rsp, 40h
0x1800364e3  mov     r9, [rdx+10h]
0x1800364e7  mov     r12, r8
0x1800364ea  mov     r15, rdx
0x1800364ed  mov     r13, rcx
0x1800364f0  test    r9, r9
0x1800364f3  jz      loc_1800366E4
0x1800364f9  lea     rax, [r9+1Ah]
0x1800364fd  cmp     rax, r9
0x180036500  jbe     loc_1800367C9
0x180036506  mov     [rbp+var_10], rax
0x18003650a  mov     eax, [rdx+18h]
0x18003650d  mov     ebx, 80041016h
0x180036512  mov     [rbp+var_18], eax
0x180036515  lea     r14, WPP_GLOBAL_Control
0x18003651c  mov     [rbp+var_20], r9
0x180036520  mov     edi, 1
0x180036525  test    r9, r9
0x180036528  jz      loc_180036776
0x18003652e  cmp     eax, 1Ah
0x180036531  jb      loc_180036771
0x180036537  mov     eax, [r9]
0x18003653a  lea     ecx, [rbx+2Bh]
0x18003653d  add     eax, edi
0x18003653f  test    eax, 0FFFFFFFEh
0x180036544  jnz     short loc_18003656C
0x180036546  mov     rax, [r9+4]
0x18003654a  cmp     rax, cs:?s_abSignature@CWbemDataPacket@@1PAEA; uchar near * CWbemDataPacket::s_abSignature
0x180036551  jnz     short loc_18003656C
0x180036553  cmp     byte ptr [r9+19h], 4
0x180036558  jnb     loc_1800366F1
0x18003655e  cmp     dil, [r9+18h]
0x180036562  sbb     ebx, ebx
0x180036564  and     ebx, 80041040h
0x18003656a  jmp     short loc_18003656E
0x18003656c  mov     ebx, ecx
0x18003656e  cmp     ebx, ecx
0x180036570  jnz     loc_180036644
0x180036576  test    ebx, ebx
0x180036578  jnz     loc_18003668D
0x18003657e  lea     r9, [r13+28h]; struct CWbemClassCache *
0x180036582  mov     [r13+68h], bl
0x180036586  lea     r8, [rbp+arg_18]; struct IWbemClassObject ***
0x18003658a  mov     [rbp+pExceptionObject], ebx
0x18003658d  lea     rdx, [rbp+pExceptionObject]; int *
0x180036591  mov     [rbp+arg_18], 0
0x180036599  lea     rcx, [rbp+var_20]; this
0x18003659d  call    ?UnmarshalPacket@CWbemObjSinkIndicatePacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z; CWbemObjSinkIndicatePacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)
0x1800365a2  mov     r12d, eax
0x1800365a5  test    eax, eax
0x1800365a7  js      short loc_1800365EF
0x1800365a9  mov     rcx, [r13+20h]
0x1800365ad  mov     r13, [rbp+arg_18]
0x1800365b1  mov     edx, [rbp+pExceptionObject]
0x1800365b4  mov     r8, r13
0x1800365b7  mov     rax, [rcx]
0x1800365ba  mov     rax, [rax+18h]
0x1800365be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365c3  mov     r12d, eax
0x1800365c6  cmp     [rbp+pExceptionObject], ebx
0x1800365c9  jle     short loc_1800365E6
0x1800365cb  movsxd  rax, ebx
0x1800365ce  mov     rcx, [r13+rax*8+0]
0x1800365d3  mov     rax, [rcx]
0x1800365d6  mov     rax, [rax+10h]
0x1800365da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365df  add     ebx, edi
0x1800365e1  cmp     ebx, [rbp+pExceptionObject]
0x1800365e4  jl      short loc_1800365CB
0x1800365e6  mov     rcx, r13
0x1800365e9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800365ef  mov     rcx, [rbp+arg_10]
0x1800365f3  lea     r8, IID_IWbemObjectSink
0x1800365fa  mov     dword ptr [r15+18h], 4
0x180036602  mov     rdx, r15
0x180036605  mov     rax, [rcx]
0x180036608  mov     rax, [rax+18h]
0x18003660c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036611  mov     ebx, eax
0x180036613  test    eax, eax
0x180036615  js      loc_18003675B
0x18003661b  mov     rcx, [r15+10h]
0x18003661f  mov     [rcx], r12d
0x180036622  mov     rcx, cs:WPP_GLOBAL_Control
0x180036629  cmp     rcx, r14
0x18003662c  jnz     loc_1800366FB
0x180036632  mov     eax, ebx
0x180036634  add     rsp, 40h
0x180036638  pop     r15
0x18003663a  pop     r14
0x18003663c  pop     r13
0x18003663e  pop     r12
0x180036640  pop     rdi
0x180036641  pop     rbx
0x180036642  pop     rbp
0x180036643  retn
0x180036644  test    ebx, ebx
0x180036646  js      loc_180036776
0x18003664c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036653  cmp     rcx, r14
0x180036656  jz      loc_180036576
0x18003665c  test    [rcx+1Ch], dil
0x180036660  jz      loc_180036576
0x180036666  cmp     byte ptr [rcx+19h], 2
0x18003666a  jb      loc_180036576
0x180036670  mov     rcx, [rcx+10h]
0x180036674  lea     r8, WPP_172c0f1e86c2386173baa66c351dfc86_Traceguids
0x18003667b  mov     edx, 0Ah
0x180036680  mov     r9d, ebx
0x180036683  call    WPP_SF_d
0x180036688  jmp     loc_180036576
0x18003668d  mov     rax, [r13+8]
0x180036691  mov     r8, r12
0x180036694  mov     rdx, r15
0x180036697  mov     rcx, [rax+20h]
0x18003669b  mov     rax, [rcx]
0x18003669e  mov     rax, [rax+28h]
0x1800366a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366a7  xor     ecx, ecx
0x1800366a9  mov     ebx, eax
0x1800366ab  test    eax, eax
0x1800366ad  jnz     short loc_180036716
0x1800366af  cmp     [r13+68h], cl
0x1800366b3  jz      short loc_18003671A
0x1800366b5  mov     rax, [r15+10h]
0x1800366b9  cmp     [rax], ecx
0x1800366bb  jnz     short loc_18003671A
0x1800366bd  mov     dword ptr [rax], 400FFh
0x1800366c3  mov     [r13+68h], cl
0x1800366c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366ce  cmp     rcx, r14
0x1800366d1  jz      short loc_1800366DD
0x1800366d3  test    [rcx+1Ch], dil
0x1800366d7  jnz     loc_1800367A2
0x1800366dd  xor     eax, eax
0x1800366df  jmp     loc_180036634
0x1800366e4  mov     [rbp+var_10], 0
0x1800366ec  jmp     loc_18003650A
0x1800366f1  mov     ebx, 8004103Fh
0x1800366f6  jmp     loc_18003656E
0x1800366fb  test    [rcx+1Ch], dil
0x1800366ff  jz      loc_180036632
0x180036705  cmp     byte ptr [rcx+19h], 2
0x180036709  jb      loc_180036632
0x18003670f  mov     edx, 20h ; ' '
0x180036714  jmp     short loc_180036743
0x180036716  test    ebx, ebx
0x180036718  js      short loc_18003678C
0x18003671a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036721  cmp     rcx, r14
0x180036724  jz      loc_180036632
0x18003672a  test    [rcx+1Ch], dil
0x18003672e  jz      loc_180036632
0x180036734  cmp     byte ptr [rcx+19h], 2
0x180036738  jb      loc_180036632
0x18003673e  mov     edx, 1Fh
0x180036743  mov     rcx, [rcx+10h]
0x180036747  lea     r8, WPP_370c3275099832fea2075eaa2fb282a8_Traceguids
0x18003674e  mov     r9d, ebx
0x180036751  call    WPP_SF_d
0x180036756  jmp     loc_180036632
0x18003675b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036761  mov     rcx, rax
0x180036764  mov     edx, ebx
0x180036766  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003676c  jmp     loc_180036622
0x180036771  mov     ebx, 8004103Ch
0x180036776  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003677c  mov     rcx, rax
0x18003677f  mov     edx, ebx
0x180036781  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036787  jmp     loc_18003664C
0x18003678c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036792  mov     rcx, rax
0x180036795  mov     edx, ebx
0x180036797  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003679d  jmp     loc_18003671A
0x1800367a2  cmp     byte ptr [rcx+19h], 2
0x1800367a6  jb      loc_1800366DD
0x1800367ac  mov     rcx, [rcx+10h]
0x1800367b0  lea     r8, WPP_370c3275099832fea2075eaa2fb282a8_Traceguids
0x1800367b7  mov     edx, 1Eh
0x1800367bc  xor     r9d, r9d
0x1800367bf  call    WPP_SF_d
0x1800367c4  jmp     loc_1800366DD
0x1800367c9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800367cf  mov     rcx, rax
0x1800367d2  mov     edx, 0FFFFFFFEh
0x1800367d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800367dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367e4  lea     r14, WPP_GLOBAL_Control
0x1800367eb  cmp     rcx, r14
0x1800367ee  jz      short loc_18003681B
0x1800367f0  mov     edi, 1
0x1800367f5  test    [rcx+1Ch], dil
0x1800367f9  jz      short loc_18003681B
0x1800367fb  cmp     byte ptr [rcx+19h], 2
0x1800367ff  jb      short loc_18003681B
0x180036801  mov     rcx, [rcx+10h]
0x180036805  lea     edx, [rdi+0Fh]
0x180036808  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18003680f  lea     r8, WPP_7c35078de6b730c8b6b4841e12630b85_Traceguids
0x180036816  call    WPP_SF_s
0x18003681b  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180036822  mov     [rbp+pExceptionObject], 57h ; 'W'
0x180036829  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003682d  call    _CxxThrowException_0
```
