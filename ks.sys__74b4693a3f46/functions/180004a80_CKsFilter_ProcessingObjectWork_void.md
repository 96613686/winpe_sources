# CKsFilter::ProcessingObjectWork(void)

- ea: `0x180004a80`
- end: `0x180004e83`
- name: `?ProcessingObjectWork@CKsFilter@@UEAAXXZ`
- size: `1027`
- prototype: `void __fastcall(CKsFilter *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callees

- `0x180004a80`
- `0x180004e8c`
- `0x18000513c`
- `0x180005a00`
- `0x180005a40`
- `0x18000b7bc`
- `0x18000dc3c`
- `0x180019c60`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180004ab9`
- `ntoskrnl!KeGetCurrentIrql` at `0x180004ab9`
- `ntoskrnl!KeReadStateMutex` at `0x180004bcb`
- `ntoskrnl!KeReadStateMutex` at `0x180004bcb`
- `ntoskrnl!KeWaitForSingleObject` at `0x180004add`
- `ntoskrnl!KeWaitForSingleObject` at `0x180004bff`
- `ntoskrnl!KeWaitForSingleObject` at `0x180004add`
- `ntoskrnl!KeWaitForSingleObject` at `0x180004bff`

## pseudocode

```c
void __fastcall CKsFilter::ProcessingObjectWork(CKsFilter *this)
{
  _KSPSTREAM_POINTER *v2; // r13
  KIRQL CurrentIrql; // al
  KSTOPOLOGY_CONNECTION **p_m_DefaultConnections; // rcx
  unsigned __int8 *p_m_ProcessPassive; // r8
  char LowPart; // r12
  CKsPinFactory **p_m_PinFactories; // r14
  struct _KSPPROCESSPIPESECTION *Flink; // rdi
  int v9; // esi
  char v10; // al
  struct _LIST_ENTRY **p_Blink; // r15
  struct _KSPPROCESSPIPESECTION *Blink; // rdi
  struct _KSPPROCESSPIPESECTION *v13; // rdi
  struct _KSPPROCESSPIPESECTION *i; // rdi
  PKSSTREAM_HEADER StreamHeader; // rdi
  _KSPSTREAM_POINTER *StreamPointer; // rax
  bool v17; // zf
  LARGE_INTEGER Timeout; // [rsp+88h] [rbp+10h] BYREF
  _KSPSTREAM_POINTER *v19; // [rsp+90h] [rbp+18h]
  _KSPSTREAM_POINTER *v20; // [rsp+98h] [rbp+20h]

  v2 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      85,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  CurrentIrql = KeGetCurrentIrql();
  p_m_DefaultConnections = &this->m_DefaultConnections;
  if ( CurrentIrql )
  {
    LODWORD(this->m_PowerEntry.PowerNotify) = 1;
    if ( KeReadStateMutex((PRKMUTEX)p_m_DefaultConnections) != 1
      || (Timeout.QuadPart = 0, KeWaitForSingleObject(&this->m_DefaultConnections, Executive, 0, 0, &Timeout) == 258) )
    {
      LODWORD(this->m_PowerEntry.PowerNotify) = 2;
      return;
    }
    LODWORD(this->m_PowerEntry.PowerNotify) = 0;
  }
  else
  {
    KeWaitForSingleObject(p_m_DefaultConnections, Executive, 0, 0, 0);
  }
  p_m_ProcessPassive = &this->m_ProcessPassive;
  while ( 1 )
  {
    LowPart = 0;
    LOBYTE(Timeout.LowPart) = 0;
    if ( !*(_DWORD *)&this->m_ProcessPassive )
      break;
LABEL_17:
    p_m_ProcessPassive = &this->m_ProcessPassive;
    if ( *(_DWORD *)&this->m_ProcessPassive )
    {
      if ( !LowPart )
        KsGateTurnInputOn((PKSGATE)&this->m_ProcessPassive);
      if ( !KsGateCaptureThreshold((PKSGATE)p_m_ProcessPassive) )
        goto LABEL_25;
    }
    else if ( LowPart )
    {
      goto LABEL_25;
    }
  }
  p_m_PinFactories = &this->m_PinFactories;
  if ( *p_m_PinFactories != (CKsPinFactory *)p_m_PinFactories
    || (struct _LIST_ENTRY **)this->m_InputPipes.Blink != &this->m_InputPipes.Blink )
  {
    v19 = 0;
    _InterlockedExchange((volatile __int32 *)&this->m_CloseEvent, 0);
    Flink = (struct _KSPPROCESSPIPESECTION *)*p_m_PinFactories;
    v9 = 0;
    v20 = 0;
    if ( Flink == (struct _KSPPROCESSPIPESECTION *)p_m_PinFactories )
    {
      v10 = BYTE2(this->m_DispatchWake);
    }
    else
    {
      do
      {
        if ( !CKsFilter::PrepareProcessPipeSection(
                (CKsFilter *)((char *)this - 8),
                Flink,
                (unsigned __int8)p_m_ProcessPassive) )
        {
          StreamPointer = Flink->StreamPointer;
          if ( !StreamPointer || (v9 = -1073741802, StreamPointer->Public.Offset->Count) )
            v9 = 259;
        }
        v10 = BYTE2(this->m_DispatchWake);
        if ( v10 && v9 != 259 )
        {
          if ( Flink->Requestor || (CKsPinFactory **)Flink->ListEntry.Flink != p_m_PinFactories || Flink->Outputs )
          {
            BYTE2(this->m_DispatchWake) = 0;
            v10 = 0;
          }
          else
          {
            v19 = Flink->StreamPointer;
          }
        }
        Flink = (struct _KSPPROCESSPIPESECTION *)Flink->ListEntry.Flink;
      }
      while ( Flink != (struct _KSPPROCESSPIPESECTION *)p_m_PinFactories );
      v2 = v20;
      LowPart = (char)v20;
    }
    p_Blink = &this->m_InputPipes.Blink;
    Blink = (struct _KSPPROCESSPIPESECTION *)this->m_InputPipes.Blink;
    if ( Blink != (struct _KSPPROCESSPIPESECTION *)&this->m_InputPipes.Blink )
    {
      do
      {
        v17 = CKsFilter::PrepareProcessPipeSection(
                (CKsFilter *)((char *)this - 8),
                Blink,
                (unsigned __int8)p_m_ProcessPassive) == 0;
        v10 = BYTE2(this->m_DispatchWake);
        if ( v17 )
          v9 = 259;
        if ( v10 && v9 != 259 )
        {
          if ( Blink->Requestor && (struct _LIST_ENTRY **)Blink->ListEntry.Flink == p_Blink && !Blink->Inputs )
          {
            v2 = Blink->StreamPointer;
          }
          else
          {
            BYTE2(this->m_DispatchWake) = 0;
            v10 = 0;
          }
        }
        Blink = (struct _KSPPROCESSPIPESECTION *)Blink->ListEntry.Flink;
      }
      while ( Blink != (struct _KSPPROCESSPIPESECTION *)p_Blink );
      LowPart = Timeout.LowPart;
      p_m_PinFactories = &this->m_PinFactories;
    }
    if ( v9 != 259 )
    {
      if ( v10 )
      {
        if ( v19 )
        {
          if ( v2 )
          {
            StreamHeader = v2->Public.StreamHeader;
            if ( !StreamHeader[-1].Duration
              && v19->Queue->CloneStreamPointer(
                   v19->Queue,
                   (_KSPSTREAM_POINTER **)&StreamHeader[-1].Duration,
                   0,
                   0,
                   v19,
                   KSPSTREAM_POINTER_TYPE_NORMAL) < 0 )
            {
              StreamHeader[-1].Duration = 0;
            }
          }
        }
      }
      if ( v9 != -1073741802 )
        v9 = ((__int64 (__fastcall *)(unsigned __int64 *, struct _LIST_ENTRY *, unsigned __int8 *))this->m_Worker)(
               &this->m_Ext.EventList.SpinLock,
               this->m_OutputPipes.Blink,
               p_m_ProcessPassive);
    }
    v13 = (struct _KSPPROCESSPIPESECTION *)*p_m_PinFactories;
    v2 = 0;
    Timeout.LowPart = 0;
    while ( v13 != (struct _KSPPROCESSPIPESECTION *)p_m_PinFactories )
    {
      CKsFilter::UnprepareProcessPipeSection((CKsFilter *)((char *)this - 8), v13, (unsigned int *)&Timeout, 0);
      v13 = (struct _KSPPROCESSPIPESECTION *)v13->ListEntry.Flink;
    }
    for ( i = (struct _KSPPROCESSPIPESECTION *)*p_Blink;
          i != (struct _KSPPROCESSPIPESECTION *)p_Blink;
          i = (struct _KSPPROCESSPIPESECTION *)i->ListEntry.Flink )
    {
      CKsFilter::UnprepareProcessPipeSection((CKsFilter *)((char *)this - 8), i, (unsigned int *)&Timeout, 0);
    }
    if ( v9 != -1073741802 && (v9 == 259 || v9 < 0) )
    {
      KsGateTurnInputOn((PKSGATE)&this->m_ProcessPassive);
      if ( !LODWORD(this->m_CloseEvent) )
        goto LABEL_25;
      LowPart = 1;
    }
    goto LABEL_17;
  }
  KsGateTurnInputOn((PKSGATE)p_m_ProcessPassive);
LABEL_25:
  CKsFilter::ReleaseProcessSync((CKsFilter *)((char *)this - 8));
}

```

## disassembly

```asm
0x180004a80  mov     [rsp+arg_0], rbx
0x180004a85  push    rbp
0x180004a86  push    rsi
0x180004a87  push    rdi
0x180004a88  push    r12
0x180004a8a  push    r13
0x180004a8c  push    r14
0x180004a8e  push    r15
0x180004a90  sub     rsp, 40h
0x180004a94  mov     rbx, rcx
0x180004a97  xor     r13d, r13d
0x180004a9a  lea     rax, WPP_RECORDER_INITIALIZED
0x180004aa1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180004aa8  lea     esi, [r13+1]
0x180004aac  jnz     loc_180004D0C
0x180004ab2  lea     rdi, [rbx+288h]
0x180004ab9  call    cs:__imp_KeGetCurrentIrql
0x180004ac0  nop     dword ptr [rax+rax+00h]
0x180004ac5  mov     rcx, rdi; Mutex
0x180004ac8  test    al, al
0x180004aca  jnz     loc_180004BC5
0x180004ad0  xor     r9d, r9d; Alertable
0x180004ad3  mov     [rsp+78h+Timeout], r13; Timeout
0x180004ad8  xor     r8d, r8d; WaitMode
0x180004adb  xor     edx, edx; WaitReason
0x180004add  call    cs:__imp_KeWaitForSingleObject
0x180004ae4  nop     dword ptr [rax+rax+00h]
0x180004ae9  lea     rbp, [rbx-8]
0x180004aed  lea     r8, [rbx+250h]; unsigned __int8
0x180004af4  mov     r12b, r13b
0x180004af7  mov     byte ptr [rsp+78h+arg_8], r13b
0x180004aff  cmp     [rbp+258h], r13d
0x180004b06  jnz     loc_180004BAA
0x180004b0c  lea     r14, [rbx+1D0h]
0x180004b13  cmp     [r14], r14
0x180004b16  jz      loc_180004CEF
0x180004b1c  xor     eax, eax
0x180004b1e  mov     [rsp+78h+arg_10], r13
0x180004b26  xchg    eax, [rbx+2D0h]
0x180004b2c  mov     rdi, [r14]
0x180004b2f  mov     esi, r13d
0x180004b32  mov     [rsp+78h+arg_18], r13
0x180004b3a  cmp     rdi, r14
0x180004b3d  jnz     loc_180004D52
0x180004b43  mov     al, [rbx+24Ah]
0x180004b49  lea     r15, [rbx+1E0h]
0x180004b50  mov     rdi, [r15]
0x180004b53  cmp     rdi, r15
0x180004b56  jnz     loc_180004DD5
0x180004b5c  cmp     esi, 103h
0x180004b62  jnz     loc_180004C6E
0x180004b68  mov     rdi, [r14]
0x180004b6b  xor     r13d, r13d
0x180004b6e  mov     dword ptr [rsp+78h+arg_8], r13d
0x180004b76  cmp     rdi, r14
0x180004b79  jnz     loc_180004E3B
0x180004b7f  mov     rdi, [r15]
0x180004b82  jmp     short loc_180004B9D
0x180004b84  xor     r9d, r9d; unsigned __int8
0x180004b87  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x180004b8f  mov     rdx, rdi; struct _KSPPROCESSPIPESECTION *
0x180004b92  mov     rcx, rbp; this
0x180004b95  call    ?UnprepareProcessPipeSection@CKsFilter@@QEAAXPEAU_KSPPROCESSPIPESECTION@@PEAKE@Z; CKsFilter::UnprepareProcessPipeSection(_KSPPROCESSPIPESECTION *,ulong *,uchar)
0x180004b9a  mov     rdi, [rdi]
0x180004b9d  cmp     rdi, r15
0x180004ba0  jnz     short loc_180004B84
0x180004ba2  cmp     esi, 0C0000016h
0x180004ba8  jnz     short loc_180004C22
0x180004baa  lea     r8, [rbx+250h]
0x180004bb1  cmp     [r8], r13d
0x180004bb4  jnz     loc_180004E61
0x180004bba  test    r12b, r12b
0x180004bbd  jz      loc_180004AF4
0x180004bc3  jmp     short loc_180004C43
0x180004bc5  mov     [rbx+278h], esi
0x180004bcb  call    cs:__imp_KeReadStateMutex
0x180004bd2  nop     dword ptr [rax+rax+00h]
0x180004bd7  cmp     eax, esi
0x180004bd9  jnz     loc_180004D43
0x180004bdf  lea     rax, [rsp+78h+arg_8]
0x180004be7  mov     qword ptr [rsp+78h+arg_8], r13
0x180004bef  xor     r9d, r9d; Alertable
0x180004bf2  mov     [rsp+78h+Timeout], rax; Timeout
0x180004bf7  xor     r8d, r8d; WaitMode
0x180004bfa  xor     edx, edx; WaitReason
0x180004bfc  mov     rcx, rdi; Object
0x180004bff  call    cs:__imp_KeWaitForSingleObject
0x180004c06  nop     dword ptr [rax+rax+00h]
0x180004c0b  cmp     eax, 102h
0x180004c10  jz      loc_180004D43
0x180004c16  mov     [rbx+278h], r13d
0x180004c1d  jmp     loc_180004AE9
0x180004c22  cmp     esi, 103h
0x180004c28  jnz     short loc_180004C64
0x180004c2a  lea     rcx, [rbx+250h]; Gate
0x180004c31  call    KsGateTurnInputOn
0x180004c36  cmp     [rbx+2D0h], r13d
0x180004c3d  jnz     loc_180004E59
0x180004c43  mov     rcx, rbp; this
0x180004c46  call    ?ReleaseProcessSync@CKsFilter@@QEAAXXZ; CKsFilter::ReleaseProcessSync(void)
0x180004c4b  mov     rbx, [rsp+78h+arg_0]
0x180004c53  add     rsp, 40h
0x180004c57  pop     r15
0x180004c59  pop     r14
0x180004c5b  pop     r13
0x180004c5d  pop     r12
0x180004c5f  pop     rdi
0x180004c60  pop     rsi
0x180004c61  pop     rbp
0x180004c62  retn
0x180004c64  test    esi, esi
0x180004c66  jns     loc_180004BAA
0x180004c6c  jmp     short loc_180004C2A
0x180004c6e  test    al, al
0x180004c70  jz      short loc_180004CC2
0x180004c72  mov     rdx, [rsp+78h+arg_10]
0x180004c7a  test    rdx, rdx
0x180004c7d  jz      short loc_180004CC2
0x180004c7f  test    r13, r13
0x180004c82  jz      short loc_180004CC2
0x180004c84  mov     rdi, [r13+70h]
0x180004c88  cmp     qword ptr [rdi-20h], 0
0x180004c8d  jnz     short loc_180004CC2
0x180004c8f  mov     rcx, [rdx+48h]
0x180004c93  xor     r9d, r9d
0x180004c96  mov     [rsp+78h+var_50], 0
0x180004c9e  xor     r8d, r8d
0x180004ca1  mov     [rsp+78h+Timeout], rdx
0x180004ca6  lea     rdx, [rdi-20h]
0x180004caa  mov     rax, [rcx]
0x180004cad  mov     rax, [rax+58h]
0x180004cb1  call    _guard_dispatch_icall
0x180004cb6  test    eax, eax
0x180004cb8  jns     short loc_180004CC2
0x180004cba  mov     qword ptr [rdi-20h], 0
0x180004cc2  cmp     esi, 0C0000016h
0x180004cc8  jz      loc_180004B68
0x180004cce  mov     rax, [rbx+228h]
0x180004cd5  lea     rcx, [rbx+0D0h]
0x180004cdc  mov     rdx, [rbx+1F0h]
0x180004ce3  call    _guard_dispatch_icall
0x180004ce8  mov     esi, eax
0x180004cea  jmp     loc_180004B68
0x180004cef  lea     rax, [rbx+1E0h]
0x180004cf6  cmp     [rax], rax
0x180004cf9  jnz     loc_180004B1C
0x180004cff  mov     rcx, r8; Gate
0x180004d02  call    KsGateTurnInputOn
0x180004d07  jmp     loc_180004C43
0x180004d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d13  cmp     [rcx+48h], r13w
0x180004d18  jz      loc_180004AB2
0x180004d1e  mov     rcx, [rcx+40h]
0x180004d22  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180004d29  mov     r9d, 55h ; 'U'
0x180004d2f  mov     [rsp+78h+Timeout], rax
0x180004d34  mov     r8d, esi
0x180004d37  mov     dl, 5
0x180004d39  call    WPP_RECORDER_SF_
0x180004d3e  jmp     loc_180004AB2
0x180004d43  mov     dword ptr [rbx+278h], 2
0x180004d4d  jmp     loc_180004C4B
0x180004d52  xor     r12d, r12d
0x180004d55  mov     r13d, 103h
0x180004d5b  mov     rdx, rdi; struct _KSPPROCESSPIPESECTION *
0x180004d5e  mov     rcx, rbp; this
0x180004d61  call    ?PrepareProcessPipeSection@CKsFilter@@QEAAEPEAU_KSPPROCESSPIPESECTION@@E@Z; CKsFilter::PrepareProcessPipeSection(_KSPPROCESSPIPESECTION *,uchar)
0x180004d66  test    al, al
0x180004d68  jnz     short loc_180004D85
0x180004d6a  mov     rax, [rdi+48h]
0x180004d6e  test    rax, rax
0x180004d71  jz      short loc_180004D82
0x180004d73  mov     rax, [rax+78h]
0x180004d77  mov     esi, 0C0000016h
0x180004d7c  cmp     [rax+8], r12d
0x180004d80  jz      short loc_180004D85
0x180004d82  mov     esi, r13d
0x180004d85  mov     al, [rbx+24Ah]
0x180004d8b  test    al, al
0x180004d8d  jz      short loc_180004DBD
0x180004d8f  cmp     esi, r13d
0x180004d92  jz      short loc_180004DBD
0x180004d94  cmp     [rdi+38h], r12
0x180004d98  jnz     short loc_180004DB3
0x180004d9a  cmp     [rdi], r14
0x180004d9d  jnz     short loc_180004DB3
0x180004d9f  cmp     [rdi+20h], r12
0x180004da3  jnz     short loc_180004DB3
0x180004da5  mov     rcx, [rdi+48h]
0x180004da9  mov     [rsp+78h+arg_10], rcx
0x180004db1  jmp     short loc_180004DBD
0x180004db3  mov     [rbx+24Ah], r12b
0x180004dba  mov     al, r12b
0x180004dbd  mov     rdi, [rdi]
0x180004dc0  cmp     rdi, r14
0x180004dc3  jnz     short loc_180004D5B
0x180004dc5  mov     r13, [rsp+78h+arg_18]
0x180004dcd  mov     r12b, r13b
0x180004dd0  jmp     loc_180004B49
0x180004dd5  xor     r14d, r14d
0x180004dd8  mov     r12d, 103h
0x180004dde  mov     rdx, rdi; struct _KSPPROCESSPIPESECTION *
0x180004de1  mov     rcx, rbp; this
0x180004de4  call    ?PrepareProcessPipeSection@CKsFilter@@QEAAEPEAU_KSPPROCESSPIPESECTION@@E@Z; CKsFilter::PrepareProcessPipeSection(_KSPPROCESSPIPESECTION *,uchar)
0x180004de9  test    al, al
0x180004deb  mov     al, [rbx+24Ah]
0x180004df1  cmovz   esi, r12d
0x180004df5  test    al, al
0x180004df7  jz      short loc_180004E1F
0x180004df9  cmp     esi, r12d
0x180004dfc  jz      short loc_180004E1F
0x180004dfe  cmp     [rdi+38h], r14
0x180004e02  jz      short loc_180004E15
0x180004e04  cmp     [rdi], r15
0x180004e07  jnz     short loc_180004E15
0x180004e09  cmp     [rdi+18h], r14
0x180004e0d  jnz     short loc_180004E15
0x180004e0f  mov     r13, [rdi+48h]
0x180004e13  jmp     short loc_180004E1F
0x180004e15  mov     [rbx+24Ah], r14b
0x180004e1c  mov     al, r14b
0x180004e1f  mov     rdi, [rdi]
0x180004e22  cmp     rdi, r15
0x180004e25  jnz     short loc_180004DDE
0x180004e27  mov     r12b, byte ptr [rsp+78h+arg_8]
0x180004e2f  lea     r14, [rbx+1D0h]
0x180004e36  jmp     loc_180004B5C
0x180004e3b  xor     r9d, r9d; unsigned __int8
0x180004e3e  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x180004e46  mov     rdx, rdi; struct _KSPPROCESSPIPESECTION *
0x180004e49  mov     rcx, rbp; this
0x180004e4c  call    ?UnprepareProcessPipeSection@CKsFilter@@QEAAXPEAU_KSPPROCESSPIPESECTION@@PEAKE@Z; CKsFilter::UnprepareProcessPipeSection(_KSPPROCESSPIPESECTION *,ulong *,uchar)
0x180004e51  mov     rdi, [rdi]
0x180004e54  jmp     loc_180004B76
0x180004e59  mov     r12b, 1
0x180004e5c  jmp     loc_180004BAA
0x180004e61  test    r12b, r12b
0x180004e64  jnz     short loc_180004E6E
0x180004e66  mov     rcx, r8; Gate
0x180004e69  call    KsGateTurnInputOn
0x180004e6e  mov     rcx, r8; Gate
0x180004e71  call    KsGateCaptureThreshold
0x180004e76  test    al, al
0x180004e78  jz      loc_180004C43
0x180004e7e  jmp     loc_180004AF4
```
