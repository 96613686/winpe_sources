# RfcommFrameWrite

- ea: `0x140013abc`
- end: `0x140013bf2`
- name: `RfcommFrameWrite`
- size: `310`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fe48`
- `0x140010260`
- `0x140011050`
- `0x1400149b4`
- `0x140014b10`
- `0x140014c64`
- `0x140014eb4`
- `0x14001513c`
- `0x1400152ec`
- `0x14001552c`
- `0x140015688`
- `0x1400162d0`

## callees

- `0x140004a68`
- `0x1400051b4`
- `0x14000df68`
- `0x140013abc`
- `0x140015c4c`
- `0x14001bfa8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140013b18`
- `ntoskrnl!ExAllocatePool2` at `0x140013b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ba1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ba1`

## pseudocode

```c
void __fastcall RfcommFrameWrite(_QWORD *a1, __int64 a2)
{
  __int64 *Pool2; // rax
  __int64 *v5; // rbx
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // r9
  int v9; // eax
  void *DeviceExtension; // rbx
  const char *v11; // rax
  int v12; // edx
  __int64 v13[9]; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      55,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a2);
  Pool2 = (__int64 *)ExAllocatePool2(64, 16, 1380345426);
  v5 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a2;
    v7 = 0;
    Pool2[1] = (__int64)a1;
    v8 = *(_QWORD *)(a2 + 120);
    if ( !v8 )
      v7 = a2 + 152;
    v9 = BrbWrite(a1[9], a1[33], a1[35], v8, v7, *(_DWORD *)(a2 + 52), (__int64)Pool2);
    v6 = v9;
    if ( v9 < 0 )
    {
      RfcommWriteComplete(v5, v9);
      ExFreePoolWithTag(v5, 0);
    }
  }
  else
  {
    v6 = -1073741670;
    v13[0] = a2;
    v13[1] = (__int64)a1;
    RfcommWriteComplete(v13, -1073741670);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v11 = NtStatusTxt(v6);
    WPP_RECORDER_SF_s(
      (_DWORD)DeviceExtension,
      v12,
      3,
      56,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      (__int64)v11);
  }
}

```

## disassembly

```asm
0x140013abc  push    rbx
0x140013abe  push    rbp
0x140013abf  push    rsi
0x140013ac0  push    rdi
0x140013ac1  push    r12
0x140013ac3  push    r14
0x140013ac5  sub     rsp, 58h
0x140013ac9  mov     rsi, rdx
0x140013acc  mov     rbp, rcx
0x140013acf  lea     r14, WPP_RECORDER_INITIALIZED
0x140013ad6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140013add  lea     r12, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013ae4  jz      short loc_140013B0A
0x140013ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x140013aed  mov     r9d, 37h ; '7'
0x140013af3  mov     [rsp+88h+var_60], rdx
0x140013af8  mov     [rsp+88h+var_68], r12
0x140013afd  mov     rcx, [rcx+40h]
0x140013b01  lea     r8d, [r9-34h]
0x140013b05  call    WPP_RECORDER_SF_q
0x140013b0a  mov     edx, 10h
0x140013b0f  mov     r8d, 52466652h
0x140013b15  lea     ecx, [rdx+30h]
0x140013b18  call    cs:__imp_ExAllocatePool2
0x140013b1f  nop     dword ptr [rax+rax+00h]
0x140013b24  mov     rbx, rax
0x140013b27  test    rax, rax
0x140013b2a  jnz     short loc_140013B49
0x140013b2c  mov     edi, 0C000009Ah
0x140013b31  mov     [rsp+88h+var_48], rsi
0x140013b36  mov     edx, edi
0x140013b38  mov     [rsp+88h+var_40], rbp
0x140013b3d  lea     rcx, [rsp+88h+var_48]
0x140013b42  call    RfcommWriteComplete
0x140013b47  jmp     short loc_140013BAD
0x140013b49  mov     [rax], rsi
0x140013b4c  xor     ecx, ecx
0x140013b4e  mov     [rax+8], rbp
0x140013b52  lea     rax, [rsi+98h]
0x140013b59  mov     r9, [rsi+78h]
0x140013b5d  mov     r8, [rbp+118h]
0x140013b64  test    r9, r9
0x140013b67  mov     rdx, [rbp+108h]
0x140013b6e  cmovz   rcx, rax
0x140013b72  mov     [rsp+88h+var_58], rbx
0x140013b77  mov     eax, [rsi+34h]
0x140013b7a  mov     dword ptr [rsp+88h+var_60], eax
0x140013b7e  mov     [rsp+88h+var_68], rcx
0x140013b83  mov     rcx, [rbp+48h]
0x140013b87  call    BrbWrite
0x140013b8c  mov     edi, eax
0x140013b8e  test    eax, eax
0x140013b90  jns     short loc_140013BAD
0x140013b92  mov     edx, eax
0x140013b94  mov     rcx, rbx
0x140013b97  call    RfcommWriteComplete
0x140013b9c  xor     edx, edx; Tag
0x140013b9e  mov     rcx, rbx; P
0x140013ba1  call    cs:__imp_ExFreePoolWithTag
0x140013ba8  nop     dword ptr [rax+rax+00h]
0x140013bad  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140013bb4  jz      short loc_140013BE4
0x140013bb6  mov     rax, cs:WPP_GLOBAL_Control
0x140013bbd  mov     ecx, edi
0x140013bbf  mov     rbx, [rax+40h]
0x140013bc3  call    NtStatusTxt
0x140013bc8  mov     r9d, 38h ; '8'
0x140013bce  mov     [rsp+88h+var_60], rax
0x140013bd3  mov     rcx, rbx
0x140013bd6  mov     [rsp+88h+var_68], r12
0x140013bdb  lea     r8d, [r9-35h]
0x140013bdf  call    WPP_RECORDER_SF_s
0x140013be4  add     rsp, 58h
0x140013be8  pop     r14
0x140013bea  pop     r12
0x140013bec  pop     rdi
0x140013bed  pop     rsi
0x140013bee  pop     rbp
0x140013bef  pop     rbx
0x140013bf0  retn
```
