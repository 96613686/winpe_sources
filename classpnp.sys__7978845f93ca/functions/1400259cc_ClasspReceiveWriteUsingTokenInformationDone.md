# ClasspReceiveWriteUsingTokenInformationDone

- ea: `0x1400259cc`
- end: `0x140025b70`
- name: `ClasspReceiveWriteUsingTokenInformationDone`
- size: `420`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140025b80`
- `0x1400262d0`

## callees

- `0x140001008`
- `0x14002001c`
- `0x140023f24`
- `0x140024070`
- `0x1400259cc`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall ClasspReceiveWriteUsingTokenInformationDone(struct _DEVICE_OBJECT **P, int a2)
{
  __int64 DeviceExtension; // r8
  __int64 v5; // r9
  unsigned __int64 v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // edx
  __int64 v14; // [rsp+30h] [rbp-59h] BYREF
  struct _DEVICE_OBJECT *v15; // [rsp+38h] [rbp-51h] BYREF
  __int64 v16; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int64 v17; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-39h] BYREF
  __int64 v19; // [rsp+70h] [rbp-19h]
  __int64 v20; // [rsp+78h] [rbp-11h]
  __int64 *v21; // [rsp+80h] [rbp-9h]
  __int64 v22; // [rsp+88h] [rbp-1h]
  struct _DEVICE_OBJECT **v23; // [rsp+90h] [rbp+7h]
  __int64 v24; // [rsp+98h] [rbp+Fh]
  __int64 *v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+A8h] [rbp+1Fh]
  unsigned __int64 *v27; // [rsp+B0h] [rbp+27h]
  __int64 v28; // [rsp+B8h] [rbp+2Fh]

  DeviceExtension = (__int64)(*P)->DeviceExtension;
  v5 = (__int64)P[40];
  v6 = MEMORY[0xFFFFF78000000008] - (_QWORD)P[58];
  v7 = *(unsigned int *)(*(_QWORD *)(DeviceExtension + 1144) + 712LL);
  v8 = *(unsigned int *)(DeviceExtension + 572);
  if ( (unsigned int)dword_14004D060 > 5 )
  {
    v9 = (__int64 *)P[6];
    v10 = *(_QWORD *)(DeviceExtension + 1168) + 4LL;
    v20 = 16;
    v19 = v10;
    v11 = *v9;
    v21 = &v14;
    v15 = P[2];
    v23 = &v15;
    v25 = &v16;
    v27 = &v17;
    v16 = v5 * v8;
    v14 = v11;
    v22 = 8;
    v24 = 8;
    v26 = 8;
    v17 = v6;
    v28 = 8;
    tlgWriteTransfer_EtwWriteTransfer(v11, (unsigned __int8 *)&unk_1400488B8, DeviceExtension, v5, 7u, &v18);
  }
  if ( P[40] == P[3] )
  {
    v12 = a2;
    return ClasspCompleteOffloadWrite(P, v12, DeviceExtension);
  }
  if ( 10000000 * v7 <= v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        263,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        *P,
        *((_DWORD *)P + 92));
    }
    v12 = -1073741823;
    return ClasspCompleteOffloadWrite(P, v12, DeviceExtension);
  }
  return ClasspContinueOffloadWrite(P);
}

```

## disassembly

```asm
0x1400259cc  mov     [rsp-8+arg_10], rbx
0x1400259d1  mov     [rsp-8+arg_18], rsi
0x1400259d6  push    rbp
0x1400259d7  push    rdi
0x1400259d8  push    r14
0x1400259da  lea     rbp, [rsp-47h]
0x1400259df  sub     rsp, 0D0h
0x1400259e6  mov     rax, cs:__security_cookie
0x1400259ed  xor     rax, rsp
0x1400259f0  mov     [rbp+57h+var_20], rax
0x1400259f4  mov     rax, [rcx]
0x1400259f7  mov     rbx, rcx
0x1400259fa  mov     rcx, [rcx+1D0h]
0x140025a01  mov     esi, edx
0x140025a03  mov     r8, [rax+40h]; int
0x140025a07  mov     rax, ds:0FFFFF78000000008h
0x140025a11  mov     r9, [rbx+140h]; int
0x140025a18  mov     rdi, rax
0x140025a1b  sub     rdi, rcx
0x140025a1e  mov     ecx, cs:dword_14004D060
0x140025a24  mov     rdx, [r8+478h]
0x140025a2b  mov     r14d, [rdx+2C8h]
0x140025a32  mov     edx, [r8+23Ch]
0x140025a39  cmp     ecx, 5
0x140025a3c  jbe     loc_140025AD5
0x140025a42  mov     rax, [rbx+30h]
0x140025a46  mov     rcx, [r8+490h]
0x140025a4d  add     rcx, 4
0x140025a51  mov     [rbp+57h+var_68], 10h
0x140025a59  imul    rdx, r9
0x140025a5d  mov     [rbp+57h+var_70], rcx
0x140025a61  mov     rcx, [rax]; int
0x140025a64  lea     rax, [rbp+57h+var_B0]
0x140025a68  mov     [rbp+57h+var_60], rax
0x140025a6c  mov     rax, [rbx+10h]
0x140025a70  mov     [rbp+57h+var_A8], rax
0x140025a74  lea     rax, [rbp+57h+var_A8]
0x140025a78  mov     [rbp+57h+var_50], rax
0x140025a7c  lea     rax, [rbp+57h+var_A0]
0x140025a80  mov     [rbp+57h+var_40], rax
0x140025a84  lea     rax, [rbp+57h+var_98]
0x140025a88  mov     [rbp+57h+var_30], rax
0x140025a8c  lea     rax, [rbp+57h+var_90]
0x140025a90  mov     [rbp+57h+var_A0], rdx
0x140025a94  lea     rdx, unk_1400488B8; int
0x140025a9b  mov     [rsp+0E0h+var_B8], rax; __int64
0x140025aa0  mov     [rsp+0E0h+var_C0], 7; ULONG
0x140025aa8  mov     [rbp+57h+var_B0], rcx
0x140025aac  mov     [rbp+57h+var_58], 8
0x140025ab4  mov     [rbp+57h+var_48], 8
0x140025abc  mov     [rbp+57h+var_38], 8
0x140025ac4  mov     [rbp+57h+var_98], rdi
0x140025ac8  mov     [rbp+57h+var_28], 8
0x140025ad0  call    _tlgWriteTransfer_EtwWriteTransfer
0x140025ad5  mov     rax, [rbx+18h]
0x140025ad9  cmp     [rbx+140h], rax
0x140025ae0  jnz     short loc_140025AEE
0x140025ae2  mov     edx, esi
0x140025ae4  mov     rcx, rbx; P
0x140025ae7  call    ClasspCompleteOffloadWrite
0x140025aec  jmp     short loc_140025B4B
0x140025aee  imul    rcx, r14, 989680h
0x140025af5  cmp     rcx, rdi
0x140025af8  ja      short loc_140025B43
0x140025afa  mov     rcx, cs:WPP_GLOBAL_Control
0x140025b01  lea     rax, WPP_GLOBAL_Control
0x140025b08  cmp     rcx, rax
0x140025b0b  jz      short loc_140025B3C
0x140025b0d  mov     eax, [rcx+2Ch]
0x140025b10  test    al, 10h
0x140025b12  jz      short loc_140025B3C
0x140025b14  cmp     byte ptr [rcx+29h], 3
0x140025b18  jb      short loc_140025B3C
0x140025b1a  mov     eax, [rbx+170h]
0x140025b20  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140025b27  mov     r9, [rbx]
0x140025b2a  mov     edx, 107h
0x140025b2f  mov     rcx, [rcx+18h]
0x140025b33  mov     [rsp+0E0h+var_C0], eax
0x140025b37  call    WPP_SF_qD
0x140025b3c  mov     edx, 0C0000001h
0x140025b41  jmp     short loc_140025AE4
0x140025b43  mov     rcx, rbx; P
0x140025b46  call    ClasspContinueOffloadWrite
0x140025b4b  mov     rcx, [rbp+57h+var_20]
0x140025b4f  xor     rcx, rsp; StackCookie
0x140025b52  call    __security_check_cookie
0x140025b57  lea     r11, [rsp+0E0h+var_10]
0x140025b5f  mov     rbx, [r11+30h]
0x140025b63  mov     rsi, [r11+38h]
0x140025b67  mov     rsp, r11
0x140025b6a  pop     r14
0x140025b6c  pop     rdi
0x140025b6d  pop     rbp
0x140025b6e  retn
```
