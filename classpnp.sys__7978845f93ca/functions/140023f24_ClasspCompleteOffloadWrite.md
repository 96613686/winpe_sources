# ClasspCompleteOffloadWrite

- ea: `0x140023f24`
- end: `0x140024068`
- name: `ClasspCompleteOffloadWrite`
- size: `324`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020ef4`
- `0x140024070`
- `0x1400259cc`
- `0x140025b80`
- `0x1400262d0`

## callees

- `0x140023cac`
- `0x140023e3c`
- `0x140023f24`
- `0x140027070`
- `0x140027684`

## pseudocode

```c
__int64 __fastcall ClasspCompleteOffloadWrite(struct _DEVICE_OBJECT **P, int a2, __int64 a3)
{
  struct _DEVICE_OBJECT *v3; // r14
  struct _DEVICE_OBJECT *v5; // rdx
  struct _DEVICE_OBJECT *v7; // rsi
  struct _DEVICE_OBJECT *v8; // r12
  unsigned int *DeviceExtension; // rax
  IRP *v10; // r15
  int v11; // r13d
  _DRIVER_OBJECT *v12; // rbp
  const wchar_t *v13; // rax
  struct _DEVICE_OBJECT *v15; // [rsp+90h] [rbp+8h]

  v3 = *P;
  v5 = P[45];
  v7 = P[5];
  v8 = P[2];
  DeviceExtension = (unsigned int *)(*P)->DeviceExtension;
  v10 = (IRP *)P[1];
  v11 = *((_DWORD *)P + 92);
  *(_QWORD *)&v7->Type = 0;
  v12 = (_DRIVER_OBJECT *)((_QWORD)P[40] * DeviceExtension[143]);
  v15 = v5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v13 = L"Successful";
    if ( a2 < 0 )
      v13 = L"Failed";
    WPP_SF_qSIIq(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)L"Failed",
      a3,
      (_DWORD)v3,
      (__int64)v13,
      (char)v12,
      (char)v8,
      (char)v10);
    v5 = v15;
  }
  if ( v12 && v12 < (_DRIVER_OBJECT *)v8 )
    *(_DWORD *)&v7->Type |= 1u;
  if ( *((_BYTE *)P + 372) )
    *(_DWORD *)&v7->Type |= 2u;
  v7->DriverObject = v12;
  if ( a2 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qDDII(WPP_GLOBAL_Control->AttachedDevice, v5, a3, v3, v11, a2, v5, P[40]);
  }
  v10->IoStatus.Information = 16;
  ClasspCompleteOffloadRequest(v3, v10);
  return ClasspCleanupOffloadWriteContext(P);
}

```

## disassembly

```asm
0x140023f24  mov     r11, rsp
0x140023f27  push    rbx
0x140023f28  push    rbp
0x140023f29  push    rsi
0x140023f2a  push    rdi
0x140023f2b  push    r12
0x140023f2d  push    r13
0x140023f2f  push    r14
0x140023f31  push    r15
0x140023f33  sub     rsp, 48h
0x140023f37  mov     r14, [rcx]
0x140023f3a  mov     ebx, edx
0x140023f3c  mov     rdx, [rcx+168h]
0x140023f43  mov     rdi, rcx
0x140023f46  mov     rsi, [rcx+28h]
0x140023f4a  mov     r12, [rcx+10h]
0x140023f4e  mov     rax, [r14+40h]
0x140023f52  mov     r15, [rcx+8]
0x140023f56  mov     r13d, [rcx+170h]
0x140023f5d  mov     qword ptr [rsi], 0
0x140023f64  mov     ebp, [rax+23Ch]
0x140023f6a  imul    rbp, [rcx+140h]
0x140023f72  mov     [rsp+88h+arg_0], rdx
0x140023f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f81  lea     rax, WPP_GLOBAL_Control
0x140023f88  cmp     rcx, rax
0x140023f8b  jz      short loc_140023FCC
0x140023f8d  mov     rcx, [rcx+18h]
0x140023f91  lea     rdx, aFailed; "Failed"
0x140023f98  mov     [r11-50h], r15
0x140023f9c  lea     rax, aSuccessful; "Successful"
0x140023fa3  mov     [r11-58h], r12
0x140023fa7  test    ebx, ebx
0x140023fa9  mov     [r11-60h], rbp
0x140023fad  mov     r9, r14
0x140023fb0  cmovs   rax, rdx
0x140023fb4  mov     [r11-68h], rax
0x140023fb8  call    WPP_SF_qSIIq
0x140023fbd  mov     rdx, [rsp+88h+arg_0]
0x140023fc5  lea     rax, WPP_GLOBAL_Control
0x140023fcc  test    rbp, rbp
0x140023fcf  jz      short loc_140023FD9
0x140023fd1  cmp     rbp, r12
0x140023fd4  jnb     short loc_140023FD9
0x140023fd6  or      dword ptr [rsi], 1
0x140023fd9  cmp     byte ptr [rdi+174h], 0
0x140023fe0  jz      short loc_140023FE5
0x140023fe2  or      dword ptr [rsi], 2
0x140023fe5  mov     [rsi+8], rbp
0x140023fe9  test    ebx, ebx
0x140023feb  jns     short loc_140024038
0x140023fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ff4  cmp     rcx, rax
0x140023ff7  jz      short loc_14002402C
0x140023ff9  mov     eax, [rcx+2Ch]
0x140023ffc  test    al, 10h
0x140023ffe  jz      short loc_14002402C
0x140024000  cmp     byte ptr [rcx+29h], 3
0x140024004  jb      short loc_14002402C
0x140024006  mov     rax, [rdi+140h]
0x14002400d  mov     r9, r14
0x140024010  mov     rcx, [rcx+18h]
0x140024014  mov     [rsp+88h+var_50], rax
0x140024019  mov     [rsp+88h+var_58], rdx
0x14002401e  mov     [rsp+88h+var_60], ebx
0x140024022  mov     [rsp+88h+var_68], r13d
0x140024027  call    WPP_SF_qDDII
0x14002402c  xor     eax, eax
0x14002402e  cmp     [rdi+140h], rax
0x140024035  cmovnz  ebx, eax
0x140024038  mov     r8d, ebx
0x14002403b  mov     qword ptr [r15+38h], 10h
0x140024043  mov     rdx, r15; Irp
0x140024046  mov     rcx, r14; DeviceObject
0x140024049  call    ClasspCompleteOffloadRequest
0x14002404e  mov     rcx, rdi; P
0x140024051  call    ClasspCleanupOffloadWriteContext
0x140024056  add     rsp, 48h
0x14002405a  pop     r15
0x14002405c  pop     r14
0x14002405e  pop     r13
0x140024060  pop     r12
0x140024062  pop     rdi
0x140024063  pop     rsi
0x140024064  pop     rbp
0x140024065  pop     rbx
0x140024066  retn
```
