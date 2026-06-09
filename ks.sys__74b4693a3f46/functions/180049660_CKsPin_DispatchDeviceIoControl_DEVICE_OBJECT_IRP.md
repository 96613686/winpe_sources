# CKsPin::DispatchDeviceIoControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180049660`
- end: `0x180049b0f`
- name: `?DispatchDeviceIoControl@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1199`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007210`
- `0x18000b7bc`
- `0x18000ee54`
- `0x180019c60`
- `0x180034070`
- `0x180049660`
- `0x180049c20`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180049afe`
- `ntoskrnl!KeReleaseMutex` at `0x180049afe`
- `ntoskrnl!KeWaitForSingleObject` at `0x180049abe`
- `ntoskrnl!KeWaitForSingleObject` at `0x180049abe`
- `ntoskrnl!IofCompleteRequest` at `0x180049734`
- `ntoskrnl!IofCompleteRequest` at `0x180049734`

## pseudocode

```c
__int64 __fastcall CKsPin::DispatchDeviceIoControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v4; // rbp
  __int64 v5; // rdi
  int v6; // eax
  NTSTATUS Status; // ebx
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  KSRESET ResetValue; // [rsp+88h] [rbp+10h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      85,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v4 = *(_QWORD *)(*(_QWORD *)CurrentStackLocation->FileObject->FsContext + 112LL);
  v5 = v4 - 128;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 3080219 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        88,
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
    }
    ResetValue = KSRESET_BEGIN;
    Status = KsAcquireResetValue(v2, &ResetValue);
    if ( Status >= 0 )
    {
      KeWaitForSingleObject(*(PVOID *)(v4 + 88), Executive, 0, 0, 0);
      v13 = *(_QWORD *)(v5 + 576);
      *(_DWORD *)(v4 + 252) = ResetValue;
      if ( v13 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v13 + 16) + 32LL))(*(_QWORD *)(v13 + 16), v4 - 128);
      KeReleaseMutex(*(PRKMUTEX *)(v4 + 88), 0);
    }
    goto LABEL_15;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 3080223 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        89,
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
    }
    if ( v2->RequestorMode || !CurrentStackLocation->Parameters.CreatePipe.Parameters || !v2->UserBuffer )
    {
      Status = -1073741808;
      goto LABEL_15;
    }
    if ( CurrentStackLocation->Parameters.Create.Options != 32 || CurrentStackLocation->Parameters.Read.Length != 32 )
    {
      Status = -1073741306;
      goto LABEL_11;
    }
    Status = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v5 + 32) + 48LL))(v5 + 32);
    if ( Status >= 0 )
      v2->IoStatus.Information = 32;
LABEL_15:
    if ( Status == 259 )
      return (unsigned int)Status;
    goto LABEL_11;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3096599
    && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3112979 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3080195
      || (v12 = KspHandleAutomationIoControl((int)v2, 0, 0), Status = v12, v12 == -1073741275)
      || v12 == -1073741264
      || v12 == -2147483643
      || v12 >= 0 )
    {
      Status = KspHandleAutomationIoControl((int)v2, *(_QWORD *)(v5 + 672), *(_DWORD *)(v5 + 680));
    }
    goto LABEL_15;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      86,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
  }
  if ( !*(_QWORD *)(v5 + 696) || *(_QWORD *)(v5 + 856) )
    goto LABEL_28;
  v6 = *(_DWORD *)(v4 + 244);
  if ( v6 == 1 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 3112979 )
      goto LABEL_10;
LABEL_28:
    Status = -1073741808;
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 648) + 24LL))(*(_QWORD *)(v5 + 648)) - 128;
    if ( v11 && *(_BYTE *)(v11 + 232) )
      Status = -1073741790;
    goto LABEL_11;
  }
  if ( v6 != 2 || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3096599 )
    goto LABEL_28;
LABEL_10:
  Status = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 72) + 112LL))(*(_QWORD *)(v4 + 72));
  if ( Status < 0 )
  {
LABEL_11:
    v2->IoStatus.Status = Status;
    IofCompleteRequest(v2, 0);
    return (unsigned int)Status;
  }
  if ( !*(_DWORD *)(v5 + 716) )
  {
    Status = -1073741436;
    goto LABEL_11;
  }
  if ( *(_BYTE *)(v5 + 712) )
  {
    Status = -1073741661;
    goto LABEL_11;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v5 + 984)) == 1 )
  {
    Status = -1073741436;
LABEL_25:
    CKsPin::DecrementIrpCirculation((CKsPin *)v5);
    goto LABEL_11;
  }
  v2->IoStatus.Status = 0;
  ++*(_DWORD *)(v5 + 976);
  v9 = *(_QWORD *)(v5 + 696);
  while ( v9 )
  {
    if ( v9 == v5 )
    {
      if ( Status == 259 )
      {
        Status = 0;
LABEL_46:
        if ( v2->IoStatus.Status < 0 )
          Status = v2->IoStatus.Status;
      }
      else if ( !Status )
      {
        goto LABEL_46;
      }
      v2->IoStatus.Information = v2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
      ++*(_DWORD *)(v5 + 980);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          87,
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
          (char)v2,
          *(_DWORD *)(v5 + 980));
      break;
    }
    v15 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, struct _IRP *, __int64 *))(*(_QWORD *)v9 + 24LL))(v9, v2, &v15);
    v9 = v15;
    Status = v10;
  }
  if ( Status != 259 )
    goto LABEL_25;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x180049660  mov     [rsp+arg_0], rbx
0x180049665  push    rbp
0x180049666  push    rsi
0x180049667  push    rdi
0x180049668  push    r12
0x18004966a  push    r13
0x18004966c  push    r14
0x18004966e  push    r15
0x180049670  sub     rsp, 40h
0x180049674  mov     rsi, rdx
0x180049677  xor     r14d, r14d
0x18004967a  lea     r12, WPP_RECORDER_INITIALIZED
0x180049681  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180049688  lea     r13, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18004968f  lea     r15d, [r14+1]
0x180049693  jnz     loc_180049888
0x180049699  mov     rbx, [rsi+0B8h]
0x1800496a0  mov     rax, [rbx+30h]
0x1800496a4  mov     rcx, [rax+18h]
0x1800496a8  mov     rax, [rcx]
0x1800496ab  mov     ecx, [rbx+18h]
0x1800496ae  mov     rbp, [rax+70h]
0x1800496b2  mov     eax, ecx
0x1800496b4  lea     rdi, [rbp-80h]
0x1800496b8  sub     eax, 2F001Bh
0x1800496bd  jz      loc_180049A5B
0x1800496c3  sub     eax, 4
0x1800496c6  jz      loc_1800499CC
0x1800496cc  sub     eax, 3FF8h
0x1800496d1  jnz     short loc_180049742
0x1800496d3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800496da  jnz     loc_180049907
0x1800496e0  cmp     [rdi+2B8h], r14
0x1800496e7  jz      loc_18004984F
0x1800496ed  cmp     [rdi+358h], r14
0x1800496f4  jnz     loc_18004984F
0x1800496fa  mov     eax, [rbp+0F4h]
0x180049700  cmp     eax, r15d
0x180049703  jnz     loc_18004983D
0x180049709  cmp     dword ptr [rbx+18h], 2F8013h
0x180049710  jnz     loc_18004984F
0x180049716  mov     rcx, [rbp+48h]
0x18004971a  mov     rax, [rcx]
0x18004971d  mov     rax, [rax+70h]
0x180049721  call    _guard_dispatch_icall
0x180049726  mov     ebx, eax
0x180049728  test    eax, eax
0x18004972a  jns     short loc_1800497A5
0x18004972c  xor     edx, edx; PriorityBoost
0x18004972e  mov     [rsi+30h], ebx
0x180049731  mov     rcx, rsi; Irp
0x180049734  call    cs:__imp_IofCompleteRequest
0x18004973b  nop     dword ptr [rax+rax+00h]
0x180049740  jmp     short loc_18004978A
0x180049742  cmp     eax, 3FFCh
0x180049747  jz      short loc_1800496D3
0x180049749  cmp     ecx, 2F0003h
0x18004974f  jz      loc_1800498B8
0x180049755  mov     eax, [rdi+2A8h]
0x18004975b  lea     r8, [rbp+68h]
0x18004975f  mov     rdx, [rbp+60h]
0x180049763  lea     r9, [r8+10h]
0x180049767  mov     [rsp+78h+var_50], eax; int
0x18004976b  mov     rcx, rsi; int
0x18004976e  mov     rax, [rdi+2A0h]
0x180049775  mov     [rsp+78h+Timeout], rax; __int64
0x18004977a  call    KspHandleAutomationIoControl
0x18004977f  mov     ebx, eax
0x180049781  mov     ebp, 103h
0x180049786  cmp     ebx, ebp
0x180049788  jnz     short loc_18004972C
0x18004978a  mov     eax, ebx
0x18004978c  mov     rbx, [rsp+78h+arg_0]
0x180049794  add     rsp, 40h
0x180049798  pop     r15
0x18004979a  pop     r14
0x18004979c  pop     r13
0x18004979e  pop     r12
0x1800497a0  pop     rdi
0x1800497a1  pop     rsi
0x1800497a2  pop     rbp
0x1800497a3  retn
0x1800497a5  cmp     [rdi+2CCh], r14d
0x1800497ac  jz      loc_180049937
0x1800497b2  cmp     [rdi+2C8h], r14b
0x1800497b9  jnz     loc_180049941
0x1800497bf  mov     eax, r15d
0x1800497c2  lock xadd [rdi+3D8h], eax
0x1800497ca  add     eax, r15d
0x1800497cd  cmp     eax, r15d
0x1800497d0  jz      loc_18004994B
0x1800497d6  mov     [rsi+30h], r14d
0x1800497da  add     [rdi+3D0h], r15d
0x1800497e1  mov     rcx, [rdi+2B8h]
0x1800497e8  mov     ebp, 103h
0x1800497ed  test    rcx, rcx
0x1800497f0  jz      short loc_180049828
0x1800497f2  mov     eax, ebx
0x1800497f4  cmp     rcx, rdi
0x1800497f7  jz      loc_180049955
0x1800497fd  mov     [rsp+78h+arg_10], r14
0x180049805  lea     r8, [rsp+78h+arg_10]
0x18004980d  mov     rax, [rcx]
0x180049810  mov     rdx, rsi
0x180049813  mov     rax, [rax+18h]
0x180049817  call    _guard_dispatch_icall
0x18004981c  mov     rcx, [rsp+78h+arg_10]
0x180049824  mov     ebx, eax
0x180049826  jmp     short loc_1800497E8
0x180049828  cmp     ebx, ebp
0x18004982a  jz      loc_18004978A
0x180049830  mov     rcx, rdi; this
0x180049833  call    ?DecrementIrpCirculation@CKsPin@@AEAAXXZ; CKsPin::DecrementIrpCirculation(void)
0x180049838  jmp     loc_18004972C
0x18004983d  cmp     eax, 2
0x180049840  jnz     short loc_18004984F
0x180049842  cmp     dword ptr [rbx+18h], 2F4017h
0x180049849  jz      loc_180049716
0x18004984f  mov     rcx, [rdi+288h]
0x180049856  mov     ebx, 0C0000010h
0x18004985b  mov     rax, [rcx]
0x18004985e  mov     rax, [rax+18h]
0x180049862  call    _guard_dispatch_icall
0x180049867  add     rax, 0FFFFFFFFFFFFFF80h
0x18004986b  jz      loc_18004972C
0x180049871  cmp     [rax+0E8h], r14b
0x180049878  jz      loc_18004972C
0x18004987e  mov     ebx, 0C0000022h
0x180049883  jmp     loc_18004972C
0x180049888  mov     rcx, cs:WPP_GLOBAL_Control
0x18004988f  cmp     [rcx+48h], r14w
0x180049894  jz      loc_180049699
0x18004989a  mov     rcx, [rcx+40h]
0x18004989e  mov     r9d, 55h ; 'U'
0x1800498a4  mov     r8d, r15d
0x1800498a7  mov     [rsp+78h+Timeout], r13
0x1800498ac  mov     dl, 5
0x1800498ae  call    WPP_RECORDER_SF_
0x1800498b3  jmp     loc_180049699
0x1800498b8  mov     [rsp+78h+var_50], r14d; int
0x1800498bd  lea     rdx, qword_180079430
0x1800498c4  xor     r9d, r9d
0x1800498c7  mov     [rsp+78h+Timeout], r14; __int64
0x1800498cc  xor     r8d, r8d
0x1800498cf  mov     rcx, rsi; int
0x1800498d2  call    KspHandleAutomationIoControl
0x1800498d7  mov     ebx, eax
0x1800498d9  cmp     eax, 0C0000225h
0x1800498de  jz      loc_180049755
0x1800498e4  cmp     eax, 0C0000230h
0x1800498e9  jz      loc_180049755
0x1800498ef  cmp     eax, 80000005h
0x1800498f4  jz      loc_180049755
0x1800498fa  test    eax, eax
0x1800498fc  js      loc_180049781
0x180049902  jmp     loc_180049755
0x180049907  mov     rcx, cs:WPP_GLOBAL_Control
0x18004990e  cmp     [rcx+48h], r14w
0x180049913  jz      loc_1800496E0
0x180049919  mov     rcx, [rcx+40h]
0x18004991d  mov     r9d, 56h ; 'V'
0x180049923  mov     r8d, r15d
0x180049926  mov     [rsp+78h+Timeout], r13
0x18004992b  mov     dl, 5
0x18004992d  call    WPP_RECORDER_SF_
0x180049932  jmp     loc_1800496E0
0x180049937  mov     ebx, 0C0000184h
0x18004993c  jmp     loc_18004972C
0x180049941  mov     ebx, 0C00000A3h
0x180049946  jmp     loc_18004972C
0x18004994b  mov     ebx, 0C0000184h
0x180049950  jmp     loc_180049830
0x180049955  cmp     ebx, ebp
0x180049957  jnz     short loc_18004995E
0x180049959  mov     ebx, r14d
0x18004995c  jmp     short loc_180049962
0x18004995e  test    eax, eax
0x180049960  jnz     short loc_18004996A
0x180049962  mov     eax, [rsi+30h]
0x180049965  test    eax, eax
0x180049967  cmovs   ebx, eax
0x18004996a  mov     rax, [rsi+0B8h]
0x180049971  mov     ecx, [rax+8]
0x180049974  mov     [rsi+38h], rcx
0x180049978  add     [rdi+3D4h], r15d
0x18004997f  mov     eax, [rdi+3D4h]
0x180049985  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004998c  jz      loc_180049828
0x180049992  mov     rcx, cs:WPP_GLOBAL_Control
0x180049999  cmp     [rcx+48h], r14w
0x18004999e  jz      loc_180049828
0x1800499a4  mov     rcx, [rcx+40h]
0x1800499a8  mov     r9d, 57h ; 'W'
0x1800499ae  mov     [rsp+78h+var_48], eax
0x1800499b2  xor     edx, edx
0x1800499b4  mov     qword ptr [rsp+78h+var_50], rsi
0x1800499b9  mov     [rsp+78h+Timeout], r13
0x1800499be  lea     r8d, [r9-55h]
0x1800499c2  call    WPP_RECORDER_SF_qD
0x1800499c7  jmp     loc_180049828
0x1800499cc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800499d3  jz      short loc_1800499FC
0x1800499d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499dc  cmp     [rcx+48h], r14w
0x1800499e1  jz      short loc_1800499FC
0x1800499e3  mov     rcx, [rcx+40h]
0x1800499e7  mov     r9d, 59h ; 'Y'
0x1800499ed  mov     r8d, r15d
0x1800499f0  mov     [rsp+78h+Timeout], r13
0x1800499f5  mov     dl, 5
0x1800499f7  call    WPP_RECORDER_SF_
0x1800499fc  cmp     [rsi+40h], r14b
0x180049a00  jnz     short loc_180049A51
0x180049a02  mov     rdx, [rbx+20h]
0x180049a06  test    rdx, rdx
0x180049a09  jz      short loc_180049A51
0x180049a0b  mov     r8, [rsi+70h]
0x180049a0f  test    r8, r8
0x180049a12  jz      short loc_180049A51
0x180049a14  cmp     dword ptr [rbx+10h], 20h ; ' '
0x180049a18  jnz     short loc_180049A47
0x180049a1a  cmp     dword ptr [rbx+8], 20h ; ' '
0x180049a1e  jnz     short loc_180049A47
0x180049a20  lea     rcx, [rdi+20h]
0x180049a24  mov     rax, [rcx]
0x180049a27  mov     rax, [rax+30h]
0x180049a2b  call    _guard_dispatch_icall
0x180049a30  mov     ebx, eax
0x180049a32  test    eax, eax
0x180049a34  js      loc_180049781
0x180049a3a  mov     qword ptr [rsi+38h], 20h ; ' '
0x180049a42  jmp     loc_180049781
0x180049a47  mov     ebx, 0C0000206h
0x180049a4c  jmp     loc_18004972C
0x180049a51  mov     ebx, 0C0000010h
0x180049a56  jmp     loc_180049781
0x180049a5b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180049a62  jz      short loc_180049A8B
0x180049a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a6b  cmp     [rcx+48h], r14w
0x180049a70  jz      short loc_180049A8B
0x180049a72  mov     rcx, [rcx+40h]
0x180049a76  mov     r9d, 58h ; 'X'
0x180049a7c  mov     r8d, r15d
0x180049a7f  mov     [rsp+78h+Timeout], r13
0x180049a84  mov     dl, 5
0x180049a86  call    WPP_RECORDER_SF_
0x180049a8b  lea     rdx, [rsp+78h+ResetValue]; ResetValue
0x180049a93  mov     [rsp+78h+ResetValue], r14d
0x180049a9b  mov     rcx, rsi; Irp
0x180049a9e  call    KsAcquireResetValue
0x180049aa3  mov     ebx, eax
0x180049aa5  test    eax, eax
0x180049aa7  js      loc_180049781
0x180049aad  mov     rcx, [rbp+58h]; Object
0x180049ab1  xor     r9d, r9d; Alertable
0x180049ab4  xor     r8d, r8d; WaitMode
0x180049ab7  mov     [rsp+78h+Timeout], r14; Timeout
0x180049abc  xor     edx, edx; WaitReason
0x180049abe  call    cs:__imp_KeWaitForSingleObject
0x180049ac5  nop     dword ptr [rax+rax+00h]
0x180049aca  mov     rcx, [rdi+240h]
0x180049ad1  mov     r8d, [rsp+78h+ResetValue]
0x180049ad9  mov     [rbp+0FCh], r8d
0x180049ae0  test    rcx, rcx
0x180049ae3  jz      short loc_180049AF8
0x180049ae5  mov     rcx, [rcx+10h]
0x180049ae9  mov     rdx, rdi
0x180049aec  mov     rax, [rcx]
0x180049aef  mov     rax, [rax+20h]
0x180049af3  call    _guard_dispatch_icall
0x180049af8  mov     rcx, [rbp+58h]; Mutex
0x180049afc  xor     edx, edx; Wait
0x180049afe  call    cs:__imp_KeReleaseMutex
0x180049b05  nop     dword ptr [rax+rax+00h]
0x180049b0a  jmp     loc_180049781
```
