# ClasspWriteUsingTokenTransferPacketDone

- ea: `0x1400262d0`
- end: `0x1400264c8`
- name: `ClasspWriteUsingTokenTransferPacketDone`
- size: `504`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140020ef4`
- `0x140023bc4`
- `0x140023f24`
- `0x1400259cc`
- `0x1400262d0`
- `0x140026f28`
- `0x140026f8c`
- `0x14002734c`

## pseudocode

```c
NTSTATUS __fastcall ClasspWriteUsingTokenTransferPacketDone(_QWORD *P, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  char *v5; // rdi
  __int64 v6; // rdx
  int v7; // r10d
  int v8; // edi
  char v9; // cl
  __int64 v10; // rsi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx

  v3 = *P;
  v5 = (char *)P[38];
  v6 = P[43];
  v7 = *((_DWORD *)P + 92);
  P[43] = 0;
  if ( !v5 )
    v5 = (char *)(P + 12);
  v8 = *((_DWORD *)v5 + 12);
  if ( v8 == -1073741811 || v8 == -1073740699 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 259, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v3, v8, v7);
    }
    if ( v8 == -1073740699 )
      *((_BYTE *)P + 372) = 1;
    return ClasspCompleteOffloadWrite((struct _DEVICE_OBJECT **)P, v8, a3);
  }
  else
  {
    if ( v8 >= 0 )
    {
      v9 = *(_BYTE *)(*(_QWORD *)(v6 + 288) + 3LL);
      if ( v9 == 1 || *(_QWORD *)(v6 + 360) )
      {
        if ( v9 == 1 )
        {
          v10 = P[44];
          P[45] = v10;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            goto LABEL_18;
          }
          v12 = 260;
        }
        else
        {
          v10 = *(_QWORD *)(v6 + 360);
          P[45] = v10;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            goto LABEL_18;
          }
          v12 = 261;
        }
        WPP_SF_qIID(v11->AttachedDevice, v12);
LABEL_18:
        ClasspAdvanceOffloadWritePosition(P, v10);
        return ClasspReceiveWriteUsingTokenInformationDone((struct _DEVICE_OBJECT **)P, v8);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDDD(WPP_GLOBAL_Control->AttachedDevice, 262, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    return ClasspReceiveWriteUsingTokenInformation((unsigned int *)P);
  }
}

```

## disassembly

```asm
0x1400262d0  mov     [rsp+arg_0], rbx
0x1400262d5  mov     [rsp+arg_8], rsi
0x1400262da  push    rdi
0x1400262db  sub     rsp, 40h
0x1400262df  mov     r9, [rcx]
0x1400262e2  mov     rbx, rcx
0x1400262e5  mov     rdi, [rcx+130h]
0x1400262ec  mov     rdx, [rcx+158h]
0x1400262f3  mov     r10d, [rcx+170h]
0x1400262fa  mov     r11, [r9+40h]
0x1400262fe  mov     qword ptr [rcx+158h], 0
0x140026309  test    rdi, rdi
0x14002630c  jnz     short loc_140026312
0x14002630e  lea     rdi, [rcx+60h]
0x140026312  mov     edi, [rdi+30h]
0x140026315  mov     esi, 0C0000465h
0x14002631a  cmp     edi, 0C000000Dh
0x140026320  jz      loc_14002645A
0x140026326  cmp     edi, esi
0x140026328  jz      loc_14002645A
0x14002632e  test    edi, edi
0x140026330  js      loc_140026401
0x140026336  mov     rax, [rdx+120h]
0x14002633d  mov     cl, [rax+3]
0x140026340  cmp     cl, 1
0x140026343  jz      short loc_140026353
0x140026345  cmp     qword ptr [rdx+168h], 0
0x14002634d  jz      loc_140026401
0x140026353  mov     r8, [rbx+10h]
0x140026357  cmp     cl, 1
0x14002635a  jnz     short loc_140026391
0x14002635c  mov     rsi, [rbx+160h]
0x140026363  mov     [rbx+168h], rsi
0x14002636a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026371  lea     rax, WPP_GLOBAL_Control
0x140026378  cmp     rcx, rax
0x14002637b  jz      short loc_1400263E7
0x14002637d  mov     eax, [rcx+2Ch]
0x140026380  test    al, 10h
0x140026382  jz      short loc_1400263E7
0x140026384  cmp     byte ptr [rcx+29h], 4
0x140026388  jb      short loc_1400263E7
0x14002638a  mov     edx, 104h
0x14002638f  jmp     short loc_1400263C4
0x140026391  mov     rsi, [rdx+168h]
0x140026398  mov     [rbx+168h], rsi
0x14002639f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400263a6  lea     rax, WPP_GLOBAL_Control
0x1400263ad  cmp     rcx, rax
0x1400263b0  jz      short loc_1400263E7
0x1400263b2  mov     eax, [rcx+2Ch]
0x1400263b5  test    al, 10h
0x1400263b7  jz      short loc_1400263E7
0x1400263b9  cmp     byte ptr [rcx+29h], 4
0x1400263bd  jb      short loc_1400263E7
0x1400263bf  mov     edx, 105h
0x1400263c4  mov     eax, [r11+23Ch]
0x1400263cb  mov     rcx, [rcx+18h]
0x1400263cf  mov     [rsp+48h+var_18], r10d
0x1400263d4  imul    rax, rsi
0x1400263d8  mov     [rsp+48h+var_20], r8
0x1400263dd  mov     [rsp+48h+var_28], rax
0x1400263e2  call    WPP_SF_qIID
0x1400263e7  mov     rdx, rsi
0x1400263ea  mov     rcx, rbx
0x1400263ed  call    ClasspAdvanceOffloadWritePosition
0x1400263f2  mov     edx, edi
0x1400263f4  mov     rcx, rbx; P
0x1400263f7  call    ClasspReceiveWriteUsingTokenInformationDone
0x1400263fc  jmp     loc_1400264B7
0x140026401  mov     rcx, cs:WPP_GLOBAL_Control
0x140026408  lea     rax, WPP_GLOBAL_Control
0x14002640f  cmp     rcx, rax
0x140026412  jz      short loc_140026450
0x140026414  mov     eax, [rcx+2Ch]
0x140026417  test    al, 10h
0x140026419  jz      short loc_140026450
0x14002641b  cmp     byte ptr [rcx+29h], 2
0x14002641f  jb      short loc_140026450
0x140026421  mov     rax, [rdx+120h]
0x140026428  mov     edx, 106h
0x14002642d  mov     rcx, [rcx+18h]
0x140026431  mov     [rsp+48h+var_18], r10d
0x140026436  movzx   r8d, byte ptr [rax+3]
0x14002643b  mov     dword ptr [rsp+48h+var_20], r8d
0x140026440  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140026447  mov     dword ptr [rsp+48h+var_28], edi
0x14002644b  call    WPP_SF_qDDD
0x140026450  mov     rcx, rbx; P
0x140026453  call    ClasspReceiveWriteUsingTokenInformation
0x140026458  jmp     short loc_1400264B7
0x14002645a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026461  lea     rax, WPP_GLOBAL_Control
0x140026468  cmp     rcx, rax
0x14002646b  jz      short loc_140026498
0x14002646d  mov     eax, [rcx+2Ch]
0x140026470  test    al, 10h
0x140026472  jz      short loc_140026498
0x140026474  cmp     byte ptr [rcx+29h], 2
0x140026478  jb      short loc_140026498
0x14002647a  mov     rcx, [rcx+18h]
0x14002647e  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140026485  mov     dword ptr [rsp+48h+var_20], r10d
0x14002648a  mov     edx, 103h
0x14002648f  mov     dword ptr [rsp+48h+var_28], edi
0x140026493  call    WPP_SF_qDD
0x140026498  cmp     edi, esi
0x14002649a  jnz     short loc_1400264A5
0x14002649c  mov     byte ptr [rbx+174h], 1
0x1400264a3  jmp     short loc_1400264AD
0x1400264a5  cmp     edi, 103h
0x1400264ab  jz      short loc_1400264B7
0x1400264ad  mov     edx, edi
0x1400264af  mov     rcx, rbx; P
0x1400264b2  call    ClasspCompleteOffloadWrite
0x1400264b7  mov     rbx, [rsp+48h+arg_0]
0x1400264bc  mov     rsi, [rsp+48h+arg_8]
0x1400264c1  add     rsp, 40h
0x1400264c5  pop     rdi
0x1400264c6  retn
```
