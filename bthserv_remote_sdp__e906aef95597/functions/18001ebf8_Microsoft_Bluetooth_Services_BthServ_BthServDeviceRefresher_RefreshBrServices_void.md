# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServices(void)

- ea: `0x18001ebf8`
- end: `0x18001ede7`
- name: `?RefreshBrServices@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@AEAAXXZ`
- size: `495`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001edf0`

## callees

- `0x180001b94`
- `0x180001bcc`
- `0x180012004`
- `0x18001ebf8`
- `0x18001ee00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ec9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ec9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServices(PSRWLOCK SRWLock)
{
  char v2; // bp
  bool v3; // dl
  _QWORD *v4; // rdi
  _QWORD *v5; // rsi
  PSRWLOCK v6; // r15
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx
  Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *v9; // rcx
  _QWORD *i; // rbx
  _QWORD *v11; // rcx
  _QWORD *v12; // rbx
  _QWORD *Ptr; // [rsp+50h] [rbp-38h] BYREF
  PVOID v14; // [rsp+58h] [rbp-30h]
  _QWORD v15[2]; // [rsp+60h] [rbp-28h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v14 = 0;
  v4 = operator new(0x20u);
  *v4 = v4;
  v4[1] = v4;
  v5 = v4;
  Ptr = v4;
  AcquireSRWLockExclusive(SRWLock);
  v6 = SRWLock + 2;
  if ( &Ptr != (_QWORD **)&SRWLock[2] )
  {
    *(_QWORD *)v4[1] = 0;
    v7 = (_QWORD *)*v4;
    if ( *v4 )
    {
      do
      {
        v8 = (_QWORD *)*v7;
        operator delete(v7, (const struct std::nothrow_t *)0x20);
        v7 = v8;
      }
      while ( v8 );
    }
    *v4 = v4;
    v4[1] = v4;
    Ptr = v6->Ptr;
    v5 = Ptr;
    v6->Ptr = v4;
    v14 = SRWLock[3].Ptr;
    SRWLock[3].Ptr = 0;
    v4 = v5;
  }
  LOBYTE(SRWLock[1].Ptr) = 0;
  ReleaseSRWLockExclusive(SRWLock);
  for ( i = (_QWORD *)*v4; i != v4; i = (_QWORD *)*i )
  {
    v15[1] = i[3];
    v15[0] = &Microsoft::Bluetooth::BluetoothBRAddress::`vftable';
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(
      v9,
      (const struct Microsoft::Bluetooth::BluetoothBRAddress *)v15);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  *(_QWORD *)v5[1] = 0;
  v11 = (_QWORD *)*v5;
  if ( *v5 )
  {
    do
    {
      v12 = (_QWORD *)*v11;
      operator delete(v11, (const struct std::nothrow_t *)0x20);
      v11 = v12;
    }
    while ( v12 );
  }
  operator delete(v5, (const struct std::nothrow_t *)0x20);
}

```

## disassembly

```asm
0x18001ebf8  mov     rax, rsp
0x18001ebfb  mov     [rax+8], rbx
0x18001ebff  mov     [rax+10h], rbp
0x18001ec03  mov     [rax+18h], rsi
0x18001ec07  mov     [rax+20h], rdi
0x18001ec0b  push    r13
0x18001ec0d  push    r14
0x18001ec0f  push    r15
0x18001ec11  sub     rsp, 70h
0x18001ec15  mov     r14, rcx
0x18001ec18  lea     rax, WPP_GLOBAL_Control
0x18001ec1f  mov     bpl, 1
0x18001ec22  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec29  cmp     rcx, rax
0x18001ec2c  jz      short loc_18001EC39
0x18001ec2e  cmp     byte ptr [rcx+19h], 4
0x18001ec32  jb      short loc_18001EC39
0x18001ec34  mov     dl, bpl
0x18001ec37  jmp     short loc_18001EC3B
0x18001ec39  xor     dl, dl
0x18001ec3b  lea     rax, WPP_RECORDER_INITIALIZED
0x18001ec42  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ec49  setnz   r8b
0x18001ec4d  lea     r9, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001ec54  test    dl, dl
0x18001ec56  jnz     short loc_18001EC5D
0x18001ec58  test    r8b, r8b
0x18001ec5b  jz      short loc_18001EC76
0x18001ec5d  mov     [rsp+88h+var_50], r9
0x18001ec62  mov     [rsp+88h+var_58], 0Bh
0x18001ec69  mov     r9, [rcx+28h]
0x18001ec6d  mov     rcx, [rcx+10h]
0x18001ec71  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ec76  and     [rsp+88h+var_30], 0
0x18001ec7c  mov     r13d, 20h ; ' '
0x18001ec82  mov     ecx, r13d; Size
0x18001ec85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ec8a  mov     rdi, rax
0x18001ec8d  mov     [rax], rax
0x18001ec90  mov     [rax+8], rax
0x18001ec94  mov     rsi, rax
0x18001ec97  mov     [rsp+88h+var_38], rax
0x18001ec9c  mov     rcx, r14; SRWLock
0x18001ec9f  call    cs:__imp_AcquireSRWLockExclusive
0x18001eca6  nop     dword ptr [rax+rax+00h]
0x18001ecab  lea     r15, [r14+10h]
0x18001ecaf  lea     rax, [rsp+88h+var_38]
0x18001ecb4  cmp     rax, r15
0x18001ecb7  jz      short loc_18001ECFF
0x18001ecb9  mov     rax, [rsi+8]
0x18001ecbd  and     qword ptr [rax], 0
0x18001ecc1  mov     rcx, [rsi]; void *
0x18001ecc4  test    rcx, rcx
0x18001ecc7  jz      short loc_18001ECDC
0x18001ecc9  mov     rbx, [rcx]
0x18001eccc  mov     rdx, r13; struct std::nothrow_t *
0x18001eccf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ecd4  mov     rcx, rbx
0x18001ecd7  test    rbx, rbx
0x18001ecda  jnz     short loc_18001ECC9
0x18001ecdc  mov     [rdi], rdi
0x18001ecdf  mov     [rdi+8], rdi
0x18001ece3  mov     rsi, [r15]
0x18001ece6  mov     [rsp+88h+var_38], rsi
0x18001eceb  mov     [r15], rdi
0x18001ecee  mov     rax, [r15+8]
0x18001ecf2  mov     [rsp+88h+var_30], rax
0x18001ecf7  and     qword ptr [r15+8], 0
0x18001ecfc  mov     rdi, rsi
0x18001ecff  mov     byte ptr [r14+8], 0
0x18001ed04  mov     rcx, r14; SRWLock
0x18001ed07  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ed0e  nop     dword ptr [rax+rax+00h]
0x18001ed13  mov     rbx, [rdi]
0x18001ed16  cmp     rbx, rdi
0x18001ed19  jz      short loc_18001ED3F
0x18001ed1b  mov     rax, [rbx+18h]
0x18001ed1f  mov     [rsp+88h+var_20], rax
0x18001ed24  lea     rax, ??_7BluetoothBRAddress@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::BluetoothBRAddress::`vftable'
0x18001ed2b  mov     [rsp+88h+var_28], rax
0x18001ed30  lea     rdx, [rsp+88h+var_28]; struct Microsoft::Bluetooth::BluetoothBRAddress *
0x18001ed35  call    ?RefreshBrServicesForDevice@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@AEAAJAEBVBluetoothBRAddress@45@@Z; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(Microsoft::Bluetooth::BluetoothBRAddress const &)
0x18001ed3a  mov     rbx, [rbx]
0x18001ed3d  jmp     short loc_18001ED16
0x18001ed3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed46  lea     rax, WPP_GLOBAL_Control
0x18001ed4d  cmp     rcx, rax
0x18001ed50  jz      short loc_18001ED58
0x18001ed52  cmp     byte ptr [rcx+19h], 5
0x18001ed56  jnb     short loc_18001ED5B
0x18001ed58  xor     bpl, bpl
0x18001ed5b  lea     rax, WPP_RECORDER_INITIALIZED
0x18001ed62  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ed69  setnz   r8b
0x18001ed6d  test    bpl, bpl
0x18001ed70  jnz     short loc_18001ED77
0x18001ed72  test    r8b, r8b
0x18001ed75  jz      short loc_18001ED9B
0x18001ed77  lea     rdx, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001ed7e  mov     [rsp+88h+var_50], rdx
0x18001ed83  mov     [rsp+88h+var_58], 0Ch
0x18001ed8a  mov     r9, [rcx+28h]
0x18001ed8e  mov     dl, bpl
0x18001ed91  mov     rcx, [rcx+10h]
0x18001ed95  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ed9a  nop
0x18001ed9b  mov     rax, [rsi+8]
0x18001ed9f  and     qword ptr [rax], 0
0x18001eda3  mov     rcx, [rsi]; void *
0x18001eda6  test    rcx, rcx
0x18001eda9  jz      short loc_18001EDBE
0x18001edab  mov     rbx, [rcx]
0x18001edae  mov     rdx, r13; struct std::nothrow_t *
0x18001edb1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001edb6  mov     rcx, rbx
0x18001edb9  test    rbx, rbx
0x18001edbc  jnz     short loc_18001EDAB
0x18001edbe  mov     rdx, r13; struct std::nothrow_t *
0x18001edc1  mov     rcx, rsi; void *
0x18001edc4  lea     r11, [rsp+88h+var_18]
0x18001edc9  mov     rbx, [r11+20h]
0x18001edcd  mov     rbp, [r11+28h]
0x18001edd1  mov     rsi, [r11+30h]
0x18001edd5  mov     rdi, [r11+38h]
0x18001edd9  mov     rsp, r11
0x18001eddc  pop     r15
0x18001edde  pop     r14
0x18001ede0  pop     r13
0x18001ede2  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
