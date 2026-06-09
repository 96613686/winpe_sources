# WriteOneXStopAuthenticationTelemetry

- ea: `0x18000e888`
- end: `0x18000eaad`
- name: `WriteOneXStopAuthenticationTelemetry`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e230`

## callees

- `0x180001008`
- `0x18000e888`
- `0x18001bd78`
- `0x180020250`

## pseudocode

```c
void __fastcall WriteOneXStopAuthenticationTelemetry(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  _DWORD *v3; // r8
  __int64 v4; // r9
  int v5; // r10d
  int v6; // [rsp+30h] [rbp-D0h] BYREF
  int v7; // [rsp+34h] [rbp-CCh] BYREF
  int v8; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+3Ch] [rbp-C4h] BYREF
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+4Ch] [rbp-B4h] BYREF
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+5Ch] [rbp-A4h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp-90h] BYREF
  int *v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  int *v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  _DWORD *v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+B8h] [rbp-48h]
  int *v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  int *v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  int *v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  int *v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  int *v35; // [rsp+100h] [rbp+0h]
  __int64 v36; // [rsp+108h] [rbp+8h]
  int *v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  int *v39; // [rsp+120h] [rbp+20h]
  __int64 v40; // [rsp+128h] [rbp+28h]
  int *v41; // [rsp+130h] [rbp+30h]
  __int64 v42; // [rsp+138h] [rbp+38h]
  int *v43; // [rsp+140h] [rbp+40h]
  __int64 v44; // [rsp+148h] [rbp+48h]
  int *v45; // [rsp+150h] [rbp+50h]
  __int64 v46; // [rsp+158h] [rbp+58h]
  int *v47; // [rsp+160h] [rbp+60h]
  __int64 v48; // [rsp+168h] [rbp+68h]
  int *v49; // [rsp+170h] [rbp+70h]
  __int64 v50; // [rsp+178h] [rbp+78h]

  if ( a1 && a1 != -2384 && (unsigned int)dword_18003A078 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(a1, a2, a1) )
    {
      v6 = v3[5];
      v21 = &v6;
      v23 = &v7;
      v25 = v3 + 51;
      v8 = v3[32];
      v27 = &v8;
      v9 = v3[33];
      v29 = &v9;
      v10 = v3[34];
      v31 = &v10;
      v11 = v3[35];
      v33 = &v11;
      v12 = v3[36];
      v35 = &v12;
      v13 = v3[37];
      v37 = &v13;
      v14 = v3[38];
      v39 = &v14;
      v15 = v3[39];
      v41 = &v15;
      v16 = v3[40];
      v43 = &v16;
      v17 = v3[41];
      v45 = &v17;
      v18 = v3[42];
      v47 = &v18;
      v49 = &v19;
      v22 = 4;
      v7 = v4;
      v24 = 4;
      v26 = 16;
      v28 = 4;
      v30 = 4;
      v32 = 4;
      v34 = 4;
      v36 = 4;
      v38 = 4;
      v40 = 4;
      v42 = 4;
      v44 = 4;
      v46 = 4;
      v48 = 4;
      v19 = v5;
      v50 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(v2, (unsigned __int8 *)byte_180035479, (__int64)v3, v4, 17, (__int64)v20);
    }
  }
}

```

## disassembly

```asm
0x18000e888  test    rcx, rcx
0x18000e88b  jz      locret_18000EAAC
0x18000e891  push    rbp
0x18000e892  lea     rbp, [rsp-90h]
0x18000e89a  sub     rsp, 190h
0x18000e8a1  mov     rax, cs:__security_cookie
0x18000e8a8  xor     rax, rsp
0x18000e8ab  mov     [rbp+90h+var_10], rax
0x18000e8b2  lea     rax, [rcx+950h]
0x18000e8b9  mov     r10d, edx
0x18000e8bc  mov     r8, rcx
0x18000e8bf  test    rax, rax
0x18000e8c2  jz      loc_18000EA95
0x18000e8c8  mov     r9d, [rax+1C0h]
0x18000e8cf  mov     eax, cs:dword_18003A078
0x18000e8d5  cmp     eax, 5
0x18000e8d8  jbe     loc_18000EA95
0x18000e8de  call    _tlgKeywordOn
0x18000e8e3  test    al, al
0x18000e8e5  jz      loc_18000EA95
0x18000e8eb  mov     eax, [r8+14h]
0x18000e8ef  lea     rdx, byte_180035479
0x18000e8f6  mov     [rsp+190h+var_160], eax
0x18000e8fa  lea     rax, [rsp+190h+var_160]
0x18000e8ff  mov     [rbp+90h+var_100], rax
0x18000e903  lea     rax, [rsp+190h+var_15C]
0x18000e908  mov     [rbp+90h+var_F0], rax
0x18000e90c  lea     rax, [r8+0CCh]
0x18000e913  mov     [rbp+90h+var_E0], rax
0x18000e917  mov     eax, [r8+80h]
0x18000e91e  mov     [rsp+190h+var_158], eax
0x18000e922  lea     rax, [rsp+190h+var_158]
0x18000e927  mov     [rbp+90h+var_D0], rax
0x18000e92b  mov     eax, [r8+84h]
0x18000e932  mov     [rsp+190h+var_154], eax
0x18000e936  lea     rax, [rsp+190h+var_154]
0x18000e93b  mov     [rbp+90h+var_C0], rax
0x18000e93f  mov     eax, [r8+88h]
0x18000e946  mov     [rsp+190h+var_150], eax
0x18000e94a  lea     rax, [rsp+190h+var_150]
0x18000e94f  mov     [rbp+90h+var_B0], rax
0x18000e953  mov     eax, [r8+8Ch]
0x18000e95a  mov     [rsp+190h+var_14C], eax
0x18000e95e  lea     rax, [rsp+190h+var_14C]
0x18000e963  mov     [rbp+90h+var_A0], rax
0x18000e967  mov     eax, [r8+90h]
0x18000e96e  mov     [rsp+190h+var_148], eax
0x18000e972  lea     rax, [rsp+190h+var_148]
0x18000e977  mov     [rbp+90h+var_90], rax
0x18000e97b  mov     eax, [r8+94h]
0x18000e982  mov     [rsp+190h+var_144], eax
0x18000e986  lea     rax, [rsp+190h+var_144]
0x18000e98b  mov     [rbp+90h+var_80], rax
0x18000e98f  mov     eax, [r8+98h]
0x18000e996  mov     [rsp+190h+var_140], eax
0x18000e99a  lea     rax, [rsp+190h+var_140]
0x18000e99f  mov     [rbp+90h+var_70], rax
0x18000e9a3  mov     eax, [r8+9Ch]
0x18000e9aa  mov     [rsp+190h+var_13C], eax
0x18000e9ae  lea     rax, [rsp+190h+var_13C]
0x18000e9b3  mov     [rbp+90h+var_60], rax
0x18000e9b7  mov     eax, [r8+0A0h]
0x18000e9be  mov     [rsp+190h+var_138], eax
0x18000e9c2  lea     rax, [rsp+190h+var_138]
0x18000e9c7  mov     [rbp+90h+var_50], rax
0x18000e9cb  mov     eax, [r8+0A4h]
0x18000e9d2  mov     [rsp+190h+var_134], eax
0x18000e9d6  lea     rax, [rsp+190h+var_134]
0x18000e9db  mov     [rbp+90h+var_40], rax
0x18000e9df  mov     eax, [r8+0A8h]
0x18000e9e6  mov     [rsp+190h+var_130], eax
0x18000e9ea  lea     rax, [rsp+190h+var_130]
0x18000e9ef  mov     [rbp+90h+var_30], rax
0x18000e9f3  lea     rax, [rsp+190h+var_12C]
0x18000e9f8  mov     [rbp+90h+var_20], rax
0x18000e9fc  lea     rax, [rsp+190h+var_120]
0x18000ea01  mov     [rsp+190h+var_168], rax
0x18000ea06  mov     [rsp+190h+var_170], 11h
0x18000ea0e  mov     [rbp+90h+var_F8], 4
0x18000ea16  mov     [rsp+190h+var_15C], r9d
0x18000ea1b  mov     [rbp+90h+var_E8], 4
0x18000ea23  mov     [rbp+90h+var_D8], 10h
0x18000ea2b  mov     [rbp+90h+var_C8], 4
0x18000ea33  mov     [rbp+90h+var_B8], 4
0x18000ea3b  mov     [rbp+90h+var_A8], 4
0x18000ea43  mov     [rbp+90h+var_98], 4
0x18000ea4b  mov     [rbp+90h+var_88], 4
0x18000ea53  mov     [rbp+90h+var_78], 4
0x18000ea5b  mov     [rbp+90h+var_68], 4
0x18000ea63  mov     [rbp+90h+var_58], 4
0x18000ea6b  mov     [rbp+90h+var_48], 4
0x18000ea73  mov     [rbp+90h+var_38], 4
0x18000ea7b  mov     [rbp+90h+var_28], 4
0x18000ea83  mov     [rsp+190h+var_12C], r10d
0x18000ea88  mov     [rbp+90h+var_18], 4
0x18000ea90  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000ea95  mov     rcx, [rbp+90h+var_10]
0x18000ea9c  xor     rcx, rsp; StackCookie
0x18000ea9f  call    __security_check_cookie
0x18000eaa4  add     rsp, 190h
0x18000eaab  pop     rbp
0x18000eaac  retn
```
