# EapDeleteMasterConnectionData

- ea: `0x18001ed10`
- end: `0x18001edda`
- name: `EapDeleteMasterConnectionData`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800084a0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18001b5ec`
- `0x18001ed10`
- `0x1800214f0`

## pseudocode

```c
__int64 __fastcall EapDeleteMasterConnectionData(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned int v2; // edi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx

  v1 = *a1;
  v2 = *(_DWORD *)(*a1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v3 = SupplicantSetConnProfile(v1 + 2384, 0, 0);
  v4 = v3;
  if ( !v3 )
    goto LABEL_8;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2, v3);
LABEL_8:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_D(v5[7], 49, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18001ed10  mov     [rsp+arg_0], rbx
0x18001ed15  mov     [rsp+arg_8], rsi
0x18001ed1a  push    rdi
0x18001ed1b  sub     rsp, 30h
0x18001ed1f  mov     rbx, [rcx]
0x18001ed22  mov     edi, [rbx+14h]
0x18001ed25  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed2c  lea     rsi, WPP_GLOBAL_Control
0x18001ed33  cmp     rcx, rsi
0x18001ed36  jz      short loc_18001ED56
0x18001ed38  test    dword ptr [rcx+44h], 800h
0x18001ed3f  jz      short loc_18001ED56
0x18001ed41  mov     rcx, [rcx+38h]
0x18001ed45  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001ed4c  mov     edx, 2Fh ; '/'
0x18001ed51  call    WPP_SF_
0x18001ed56  lea     rcx, [rbx+950h]
0x18001ed5d  xor     r8d, r8d
0x18001ed60  xor     edx, edx
0x18001ed62  call    SupplicantSetConnProfile
0x18001ed67  mov     ebx, eax
0x18001ed69  test    eax, eax
0x18001ed6b  jz      short loc_18001ED9B
0x18001ed6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed74  cmp     rcx, rsi
0x18001ed77  jz      short loc_18001EDC8
0x18001ed79  test    byte ptr [rcx+44h], 1
0x18001ed7d  jz      short loc_18001EDA2
0x18001ed7f  mov     rcx, [rcx+38h]
0x18001ed83  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001ed8a  mov     edx, 30h ; '0'
0x18001ed8f  mov     [rsp+38h+var_18], eax
0x18001ed93  mov     r9d, edi
0x18001ed96  call    WPP_SF_dd
0x18001ed9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eda2  cmp     rcx, rsi
0x18001eda5  jz      short loc_18001EDC8
0x18001eda7  test    dword ptr [rcx+44h], 800h
0x18001edae  jz      short loc_18001EDC8
0x18001edb0  mov     rcx, [rcx+38h]
0x18001edb4  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001edbb  mov     edx, 31h ; '1'
0x18001edc0  mov     r9d, ebx
0x18001edc3  call    WPP_SF_D
0x18001edc8  mov     rsi, [rsp+38h+arg_8]
0x18001edcd  mov     eax, ebx
0x18001edcf  mov     rbx, [rsp+38h+arg_0]
0x18001edd4  add     rsp, 30h
0x18001edd8  pop     rdi
0x18001edd9  retn
```
