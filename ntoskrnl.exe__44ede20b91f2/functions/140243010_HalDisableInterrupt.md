# HalDisableInterrupt

- ea: `0x140243010`
- end: `0x1402431c2`
- name: `HalDisableInterrupt`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140242ee4`
- `0x1402431c8`

## callees

- `0x140240f10`
- `0x140241944`
- `0x1402419d0`
- `0x140241c1c`
- `0x140243010`
- `0x140245868`
- `0x140245e6c`
- `0x1402551d4`
- `0x14046e674`
- `0x1406e8590`

## string_xrefs

- `0x140243069`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x140243177`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1402431a2`: `minkernel\hals\lib\interrupts\common\connect.c`

## pseudocode

```c
__int64 __fastcall HalDisableInterrupt(_DWORD *a1)
{
  bool v1; // zf
  int v3; // eax
  unsigned int v4; // edi
  unsigned int v6; // edi
  _DWORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  _DWORD *v10; // rsi
  __int64 v11; // rdi
  char v12; // bl
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1 == 1;
  v17 = 0;
  if ( !v1 )
  {
    dword_140F88398 = 19;
    dword_140F883CC = 375;
LABEL_7:
    dword_140F883B8 = -1;
    qword_140F883D0 = (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c";
    dword_140F883A0 = 0;
    qword_140F883C0 = 0;
    return (unsigned int)-1073741811;
  }
  v3 = a1[2];
  if ( v3 )
  {
    if ( v3 == 3 )
      return 0;
    sub_140245868(0, 19, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 436);
    return (unsigned int)-1073741811;
  }
  v6 = a1[16];
  v7 = (_DWORD *)sub_140241944(v6, v6 + 1);
  v10 = v7;
  if ( !v7 )
  {
    if ( (unsigned __int8)sub_1406E8590(0, v6, v8, v9) )
      return (unsigned int)sub_14046E674(a1);
    dword_140F88398 = 18;
    dword_140F883CC = 421;
    goto LABEL_7;
  }
  LODWORD(v17) = v7[4];
  HIDWORD(v17) = v6 + v7[5] - v7[7];
  sub_140240F10(&v17, 0, 0);
  v11 = sub_1402419D0((unsigned int)v17);
  if ( !v11 )
    sub_140245868(0, 17, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 460);
  v12 = sub_140241C1C(&qword_140FB97B8);
  v13 = *((_QWORD *)v10 + 5) + 56LL * (HIDWORD(v17) - v10[5]);
  *(_DWORD *)(v13 + 12) &= ~0x10u;
  v14 = sub_1402551D4(v11, &v17, v13);
  LOBYTE(v15) = v12;
  v4 = v14;
  sub_140245E6C(&qword_140FB97B8, v15, v16);
  return v4;
}

```

## disassembly

```asm
0x140243010  mov     [rsp+arg_8], rbx
0x140243015  mov     [rsp+arg_10], rsi
0x14024301a  push    rdi
0x14024301b  sub     rsp, 30h
0x14024301f  cmp     dword ptr [rcx], 1
0x140243022  mov     rbx, rcx
0x140243025  mov     [rsp+38h+arg_0], 0
0x14024302e  jnz     short loc_140243055
0x140243030  mov     eax, [rcx+8]
0x140243033  test    eax, eax
0x140243035  jz      short loc_14024309D
0x140243037  cmp     eax, 3
0x14024303a  jnz     loc_14024316C
0x140243040  xor     edi, edi
0x140243042  mov     rbx, [rsp+38h+arg_8]
0x140243047  mov     eax, edi
0x140243049  mov     rsi, [rsp+38h+arg_10]
0x14024304e  add     rsp, 30h
0x140243052  pop     rdi
0x140243053  retn
0x140243055  mov     cs:dword_140F88398, 13h
0x14024305f  mov     cs:dword_140F883CC, 177h
0x140243069  lea     rax, aMinkernelHalsL; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140243070  mov     cs:dword_140F883B8, 0FFFFFFFFh
0x14024307a  mov     cs:qword_140F883D0, rax
0x140243081  mov     cs:dword_140F883A0, 0
0x14024308b  mov     cs:qword_140F883C0, 0
0x140243096  mov     edi, 0C000000Dh
0x14024309b  jmp     short loc_140243042
0x14024309d  mov     edi, [rcx+40h]
0x1402430a0  mov     ecx, edi
0x1402430a2  lea     edx, [rdi+1]
0x1402430a5  call    sub_140241944
0x1402430aa  mov     rsi, rax
0x1402430ad  test    rax, rax
0x1402430b0  jz      short loc_140243130
0x1402430b2  mov     eax, [rax+10h]
0x1402430b5  xor     r8d, r8d
0x1402430b8  mov     dword ptr [rsp+38h+arg_0], eax
0x1402430bc  xor     edx, edx
0x1402430be  mov     ecx, [rsi+14h]
0x1402430c1  sub     ecx, [rsi+1Ch]
0x1402430c4  add     ecx, edi
0x1402430c6  mov     dword ptr [rsp+38h+arg_0+4], ecx
0x1402430ca  lea     rcx, [rsp+38h+arg_0]
0x1402430cf  call    sub_140240F10
0x1402430d4  mov     ecx, dword ptr [rsp+38h+arg_0]
0x1402430d8  call    sub_1402419D0
0x1402430dd  mov     rdi, rax
0x1402430e0  test    rax, rax
0x1402430e3  jz      loc_140243197
0x1402430e9  lea     rcx, qword_140FB97B8; SpinLock
0x1402430f0  call    sub_140241C1C
0x1402430f5  mov     edx, dword ptr [rsp+38h+arg_0+4]
0x1402430f9  mov     rcx, rdi
0x1402430fc  sub     edx, [rsi+14h]
0x1402430ff  mov     bl, al
0x140243101  movsxd  rdx, edx
0x140243104  imul    r8, rdx, 38h ; '8'
0x140243108  lea     rdx, [rsp+38h+arg_0]
0x14024310d  add     r8, [rsi+28h]
0x140243111  and     dword ptr [r8+0Ch], 0FFFFFFEFh
0x140243116  call    sub_1402551D4
0x14024311b  mov     dl, bl
0x14024311d  lea     rcx, qword_140FB97B8
0x140243124  mov     edi, eax
0x140243126  call    sub_140245E6C
0x14024312b  jmp     loc_140243042
0x140243130  mov     rax, cs:off_140E00910
0x140243137  mov     edx, edi
0x140243139  xor     ecx, ecx
0x14024313b  call    sub_1406E8590
0x140243140  test    al, al
0x140243142  jz      short loc_140243153
0x140243144  mov     rcx, rbx
0x140243147  call    sub_14046E674
0x14024314c  mov     edi, eax
0x14024314e  jmp     loc_140243042
0x140243153  mov     cs:dword_140F88398, 12h
0x14024315d  mov     cs:dword_140F883CC, 1A5h
0x140243167  jmp     loc_140243069
0x14024316c  xor     r8d, r8d
0x14024316f  mov     [rsp+38h+var_10], 1B4h
0x140243177  lea     rax, aMinkernelHalsL; "minkernel\\hals\\lib\\interrupts\\commo"...
0x14024317e  or      r9d, 0FFFFFFFFh
0x140243182  xor     ecx, ecx
0x140243184  mov     [rsp+38h+var_18], rax
0x140243189  lea     edx, [r8+13h]
0x14024318d  call    sub_140245868
0x140243192  jmp     loc_140243096
0x140243197  xor     r8d, r8d
0x14024319a  mov     [rsp+38h+var_10], 1CCh
0x1402431a2  lea     rax, aMinkernelHalsL; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1402431a9  or      r9d, 0FFFFFFFFh
0x1402431ad  xor     ecx, ecx
0x1402431af  mov     [rsp+38h+var_18], rax
0x1402431b4  lea     edx, [r8+11h]
0x1402431b8  call    sub_140245868
0x1402431bd  jmp     loc_1402430E9
```
