# WriteOneXStartAuthenticationTelemetry

- ea: `0x18001bbd8`
- end: `0x18001bd72`
- name: `WriteOneXStartAuthenticationTelemetry`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014e50`

## callees

- `0x180001008`
- `0x18001b044`
- `0x18001bbd8`
- `0x18001bd78`
- `0x180020250`

## pseudocode

```c
void __fastcall WriteOneXStartAuthenticationTelemetry(__int64 a1, int a2)
{
  __int64 v2; // rdi
  DWORD v5; // esi
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  char v11; // [rsp+30h] [rbp-D0h] BYREF
  char v12; // [rsp+31h] [rbp-CFh] BYREF
  char v13; // [rsp+32h] [rbp-CEh] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-C4h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  char v19[32]; // [rsp+50h] [rbp-B0h] BYREF
  int *v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  DWORD *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  __int64 v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  char *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  char *v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  char *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  int *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  int *v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+E8h] [rbp-18h]
  int *v36; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]

  if ( a1 )
  {
    v2 = a1 + 2384;
    if ( a1 != -2384 )
    {
      v5 = *(_DWORD *)(a1 + 2832);
      v14 = 0;
      v6 = IsDomainUser(v5, &v14);
      if ( (unsigned int)dword_18003A078 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_18003A078, v7, v6) )
        {
          v10 = *(unsigned int *)(a1 + 20);
          v20 = &v15;
          v15 = v10;
          v22 = &v16;
          v24 = a1 + 204;
          v11 = *(_BYTE *)(a1 + 200);
          v26 = &v11;
          v12 = *(_BYTE *)(a1 + 2376);
          v28 = &v12;
          v13 = *(_BYTE *)(v2 + 444);
          v30 = &v13;
          v32 = &v14;
          v34 = &v17;
          v36 = &v18;
          v21 = 4;
          v16 = v5;
          v23 = 4;
          v25 = 16;
          v27 = 1;
          v29 = 1;
          v31 = 1;
          v33 = 4;
          v17 = v8;
          v35 = 4;
          v18 = a2;
          v37 = 4;
          tlgWriteTransfer_EtwEventWriteTransfer(v10, (unsigned __int8 *)word_1800355DA, v8, v9, 11, (__int64)v19);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001bbd8  test    rcx, rcx
0x18001bbdb  jz      locret_18001BD71
0x18001bbe1  mov     [rsp-8+arg_8], rbx
0x18001bbe6  mov     [rsp-8+arg_10], rsi
0x18001bbeb  push    rbp
0x18001bbec  push    rdi
0x18001bbed  push    r14
0x18001bbef  lea     rbp, [rsp-10h]
0x18001bbf4  sub     rsp, 110h
0x18001bbfb  mov     rax, cs:__security_cookie
0x18001bc02  xor     rax, rsp
0x18001bc05  mov     [rbp+20h+var_20], rax
0x18001bc09  lea     rdi, [rcx+950h]
0x18001bc10  mov     r14d, edx
0x18001bc13  mov     rbx, rcx
0x18001bc16  test    rdi, rdi
0x18001bc19  jz      loc_18001BD4E
0x18001bc1f  mov     esi, [rdi+1C0h]
0x18001bc25  lea     rdx, [rsp+120h+var_EC]
0x18001bc2a  mov     ecx, esi; SessionId
0x18001bc2c  mov     [rsp+120h+var_EC], 0
0x18001bc34  call    IsDomainUser
0x18001bc39  mov     ecx, cs:dword_18003A078
0x18001bc3f  mov     r8d, eax
0x18001bc42  cmp     ecx, 5
0x18001bc45  jbe     loc_18001BD4E
0x18001bc4b  call    _tlgKeywordOn
0x18001bc50  test    al, al
0x18001bc52  jz      loc_18001BD4E
0x18001bc58  mov     ecx, [rbx+14h]
0x18001bc5b  lea     rax, [rsp+120h+var_E8]
0x18001bc60  mov     [rsp+120h+var_B0], rax
0x18001bc65  lea     rdx, word_1800355DA
0x18001bc6c  lea     rax, [rsp+120h+var_E4]
0x18001bc71  mov     [rsp+120h+var_E8], ecx
0x18001bc75  mov     [rbp+20h+var_A0], rax
0x18001bc79  lea     rax, [rbx+0CCh]
0x18001bc80  mov     [rbp+20h+var_90], rax
0x18001bc84  mov     al, [rbx+0C8h]
0x18001bc8a  mov     [rsp+120h+var_F0], al
0x18001bc8e  lea     rax, [rsp+120h+var_F0]
0x18001bc93  mov     [rbp+20h+var_80], rax
0x18001bc97  mov     al, [rbx+948h]
0x18001bc9d  mov     [rsp+120h+var_EF], al
0x18001bca1  lea     rax, [rsp+120h+var_EF]
0x18001bca6  mov     [rbp+20h+var_70], rax
0x18001bcaa  mov     al, [rdi+1BCh]
0x18001bcb0  mov     [rsp+120h+var_EE], al
0x18001bcb4  lea     rax, [rsp+120h+var_EE]
0x18001bcb9  mov     [rbp+20h+var_60], rax
0x18001bcbd  mov     eax, [rsp+120h+var_EC]
0x18001bcc1  mov     [rsp+120h+var_EC], eax
0x18001bcc5  lea     rax, [rsp+120h+var_EC]
0x18001bcca  mov     [rbp+20h+var_50], rax
0x18001bcce  lea     rax, [rsp+120h+var_E0]
0x18001bcd3  mov     [rbp+20h+var_40], rax
0x18001bcd7  lea     rax, [rsp+120h+var_DC]
0x18001bcdc  mov     [rbp+20h+var_30], rax
0x18001bce0  lea     rax, [rsp+120h+var_D0]
0x18001bce5  mov     [rsp+120h+var_F8], rax
0x18001bcea  mov     [rsp+120h+var_100], 0Bh
0x18001bcf2  mov     [rsp+120h+var_A8], 4
0x18001bcfb  mov     [rsp+120h+var_E4], esi
0x18001bcff  mov     [rbp+20h+var_98], 4
0x18001bd07  mov     [rbp+20h+var_88], 10h
0x18001bd0f  mov     [rbp+20h+var_78], 1
0x18001bd17  mov     [rbp+20h+var_68], 1
0x18001bd1f  mov     [rbp+20h+var_58], 1
0x18001bd27  mov     [rbp+20h+var_48], 4
0x18001bd2f  mov     [rsp+120h+var_E0], r8d
0x18001bd34  mov     [rbp+20h+var_38], 4
0x18001bd3c  mov     [rsp+120h+var_DC], r14d
0x18001bd41  mov     [rbp+20h+var_28], 4
0x18001bd49  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18001bd4e  mov     rcx, [rbp+20h+var_20]
0x18001bd52  xor     rcx, rsp; StackCookie
0x18001bd55  call    __security_check_cookie
0x18001bd5a  lea     r11, [rsp+120h+var_10]
0x18001bd62  mov     rbx, [r11+28h]
0x18001bd66  mov     rsi, [r11+30h]
0x18001bd6a  mov     rsp, r11
0x18001bd6d  pop     r14
0x18001bd6f  pop     rdi
0x18001bd70  pop     rbp
0x18001bd71  retn
```
