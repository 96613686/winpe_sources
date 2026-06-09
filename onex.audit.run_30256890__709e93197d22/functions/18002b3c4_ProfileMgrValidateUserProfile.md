# ProfileMgrValidateUserProfile

- ea: `0x18002b3c4`
- end: `0x18002b6c8`
- name: `ProfileMgrValidateUserProfile`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800284bc`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x18001a59c`
- `0x1800214f0`
- `0x18002b3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b63d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b63d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002b633`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002b633`

## pseudocode

```c
__int64 __fastcall ProfileMgrValidateUserProfile(unsigned int a1, unsigned int *a2)
{
  _BYTE *v4; // r11
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // r14d
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // r15d
  __int64 v12; // rcx
  unsigned int v13; // ebp
  int v14; // ebp
  int v15; // r9d
  DWORD LastError; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  int v20; // [rsp+20h] [rbp-58h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 >= 0x1C )
  {
    v7 = a2[1];
    if ( a1 != v7 )
    {
      v5 = 327689;
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      v6 = 12;
      v20 = a2[1];
      goto LABEL_8;
    }
    v8 = *a2;
    if ( (_DWORD)v8 != 2 )
    {
      v5 = 327688;
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      v9 = 13;
      goto LABEL_18;
    }
    if ( a1 - 28 < 0x20 )
    {
      v5 = 327689;
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      v6 = 14;
      v20 = 32;
      goto LABEL_8;
    }
    v10 = OneXValidateVariableBlob((_DWORD)a2, v7, a1 - 28, 28, (__int64)(a2 + 3));
    v5 = v10;
    if ( v10 )
    {
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      v9 = 15;
LABEL_27:
      v8 = v10;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v4 + 7), v9, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v8);
      goto LABEL_58;
    }
    v11 = a2[3];
    if ( v11 < 0x20 )
    {
      v5 = 327689;
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      WPP_SF_dd(*((_QWORD *)v4 + 7), 16, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v11, 32);
      goto LABEL_58;
    }
    v10 = OneXValidateVariableBlob((unsigned int)a2 + a2[4], v11, v11 - 32, 32, (__int64)a2 + a2[4] + 24);
    v5 = v10;
    if ( v10 )
    {
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      v9 = 17;
      goto LABEL_27;
    }
    v13 = *(_DWORD *)(v12 + 20);
    if ( (v13 & 1) != 0 )
    {
      if ( (v13 & 2) != 0 )
      {
        v5 = 327692;
        if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
          return v5;
        if ( (v4[68] & 1) == 0 )
          goto LABEL_59;
        v17 = 18;
        v18 = v13;
        goto LABEL_57;
      }
      v14 = *(_DWORD *)(v12 + 20) & 2;
    }
    else
    {
      v14 = *(_DWORD *)(v12 + 20) & 2;
    }
    v10 = OneXValidateVariableBlob((_DWORD)a2, v7, a1 - v11 - 28, 28, (__int64)(a2 + 5));
    v5 = v10;
    if ( v10 )
    {
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      v9 = (unsigned int)(v15 - 9);
      goto LABEL_27;
    }
    if ( !v14 )
      goto LABEL_59;
    if ( (a2[2] & 1) == 0 )
    {
      v5 = 327692;
      if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
        return v5;
      if ( (v4[68] & 1) == 0 )
        goto LABEL_59;
      WPP_SF_(*((_QWORD *)v4 + 7), 20, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids);
      goto LABEL_58;
    }
    if ( IsValidSid((char *)a2 + a2[6]) || (LastError = GetLastError(), (v5 = LastError) == 0) )
    {
LABEL_58:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_59;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_59;
    v17 = 21;
    v18 = LastError;
LABEL_57:
    WPP_SF_D(*((_QWORD *)v4 + 7), v17, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v18);
    goto LABEL_58;
  }
  v5 = 327689;
  if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
    return v5;
  if ( (v4[68] & 1) != 0 )
  {
    v6 = 11;
    v20 = 28;
LABEL_8:
    WPP_SF_dd(*((_QWORD *)v4 + 7), v6, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, a1, v20);
    goto LABEL_58;
  }
LABEL_59:
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v4 + 7), 22, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18002b3c4  push    rbx
0x18002b3c6  push    rbp
0x18002b3c7  push    rsi
0x18002b3c8  push    rdi
0x18002b3c9  push    r12
0x18002b3cb  push    r13
0x18002b3cd  push    r14
0x18002b3cf  push    r15
0x18002b3d1  sub     rsp, 38h
0x18002b3d5  mov     rdi, rdx
0x18002b3d8  mov     esi, ecx
0x18002b3da  mov     r11, cs:WPP_GLOBAL_Control
0x18002b3e1  lea     r12, WPP_GLOBAL_Control
0x18002b3e8  lea     r13, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002b3ef  cmp     r11, r12
0x18002b3f2  jz      short loc_18002B416
0x18002b3f4  test    dword ptr [r11+44h], 800h
0x18002b3fc  jz      short loc_18002B416
0x18002b3fe  mov     rcx, [r11+38h]
0x18002b402  mov     edx, 0Ah
0x18002b407  mov     r8, r13
0x18002b40a  call    WPP_SF_
0x18002b40f  mov     r11, cs:WPP_GLOBAL_Control
0x18002b416  mov     eax, 1Ch
0x18002b41b  cmp     esi, eax
0x18002b41d  jnb     short loc_18002B453
0x18002b41f  mov     ebx, 50009h
0x18002b424  cmp     r11, r12
0x18002b427  jz      loc_18002B6B5
0x18002b42d  test    byte ptr [r11+44h], 1
0x18002b432  jz      loc_18002B692
0x18002b438  lea     edx, [rax-11h]
0x18002b43b  mov     [rsp+78h+var_58], eax
0x18002b43f  mov     r9d, esi
0x18002b442  mov     rcx, [r11+38h]
0x18002b446  mov     r8, r13
0x18002b449  call    WPP_SF_dd
0x18002b44e  jmp     loc_18002B68B
0x18002b453  mov     r14d, [rdi+4]
0x18002b457  cmp     esi, r14d
0x18002b45a  jz      short loc_18002B481
0x18002b45c  mov     ebx, 50009h
0x18002b461  cmp     r11, r12
0x18002b464  jz      loc_18002B6B5
0x18002b46a  test    byte ptr [r11+44h], 1
0x18002b46f  jz      loc_18002B692
0x18002b475  mov     edx, 0Ch
0x18002b47a  mov     [rsp+78h+var_58], r14d
0x18002b47f  jmp     short loc_18002B43F
0x18002b481  mov     r9d, [rdi]
0x18002b484  cmp     r9d, 2
0x18002b488  jz      short loc_18002B4B9
0x18002b48a  mov     ebx, 50008h
0x18002b48f  cmp     r11, r12
0x18002b492  jz      loc_18002B6B5
0x18002b498  test    byte ptr [r11+44h], 1
0x18002b49d  jz      loc_18002B692
0x18002b4a3  mov     edx, 0Dh
0x18002b4a8  mov     rcx, [r11+38h]
0x18002b4ac  mov     r8, r13
0x18002b4af  call    WPP_SF_d
0x18002b4b4  jmp     loc_18002B68B
0x18002b4b9  lea     r8d, [rsi-1Ch]
0x18002b4bd  mov     ebp, 20h ; ' '
0x18002b4c2  cmp     r8d, ebp
0x18002b4c5  jnb     short loc_18002B4EC
0x18002b4c7  mov     ebx, 50009h
0x18002b4cc  cmp     r11, r12
0x18002b4cf  jz      loc_18002B6B5
0x18002b4d5  test    byte ptr [r11+44h], 1
0x18002b4da  jz      loc_18002B692
0x18002b4e0  lea     edx, [rbp-12h]
0x18002b4e3  mov     [rsp+78h+var_58], ebp
0x18002b4e7  jmp     loc_18002B43F
0x18002b4ec  lea     r15, [rdi+0Ch]
0x18002b4f0  mov     r9d, eax
0x18002b4f3  mov     edx, r14d
0x18002b4f6  mov     qword ptr [rsp+78h+var_58], r15
0x18002b4fb  mov     rcx, rdi
0x18002b4fe  call    OneXValidateVariableBlob
0x18002b503  mov     ebx, eax
0x18002b505  test    eax, eax
0x18002b507  jz      short loc_18002B527
0x18002b509  cmp     r11, r12
0x18002b50c  jz      loc_18002B6B5
0x18002b512  test    byte ptr [r11+44h], 1
0x18002b517  jz      loc_18002B692
0x18002b51d  mov     edx, 0Fh
0x18002b522  mov     r9d, eax
0x18002b525  jmp     short loc_18002B4A8
0x18002b527  mov     r15d, [r15]
0x18002b52a  cmp     r15d, ebp
0x18002b52d  jnb     short loc_18002B559
0x18002b52f  mov     ebx, 50009h
0x18002b534  cmp     r11, r12
0x18002b537  jz      loc_18002B6B5
0x18002b53d  test    byte ptr [r11+44h], 1
0x18002b542  jz      loc_18002B692
0x18002b548  mov     edx, 10h
0x18002b54d  mov     [rsp+78h+var_58], ebp
0x18002b551  mov     r9d, r15d
0x18002b554  jmp     loc_18002B442
0x18002b559  mov     ecx, [rdi+10h]
0x18002b55c  lea     r8d, [r15-20h]
0x18002b560  add     rcx, rdi
0x18002b563  mov     r9d, ebp
0x18002b566  mov     edx, r15d
0x18002b569  lea     rax, [rcx+18h]
0x18002b56d  mov     qword ptr [rsp+78h+var_58], rax
0x18002b572  call    OneXValidateVariableBlob
0x18002b577  mov     ebx, eax
0x18002b579  test    eax, eax
0x18002b57b  jz      short loc_18002B598
0x18002b57d  cmp     r11, r12
0x18002b580  jz      loc_18002B6B5
0x18002b586  test    byte ptr [r11+44h], 1
0x18002b58b  jz      loc_18002B692
0x18002b591  mov     edx, 11h
0x18002b596  jmp     short loc_18002B522
0x18002b598  mov     ebp, [rcx+14h]
0x18002b59b  test    bpl, 1
0x18002b59f  jnz     short loc_18002B5A6
0x18002b5a1  and     ebp, 2
0x18002b5a4  jmp     short loc_18002B5B3
0x18002b5a6  mov     eax, ebp
0x18002b5a8  and     eax, 2
0x18002b5ab  jnz     loc_18002B666
0x18002b5b1  mov     ebp, eax
0x18002b5b3  lea     rax, [rdi+14h]
0x18002b5b7  sub     esi, r15d
0x18002b5ba  mov     r9d, 1Ch
0x18002b5c0  mov     qword ptr [rsp+78h+var_58], rax
0x18002b5c5  mov     edx, r14d
0x18002b5c8  mov     rcx, rdi
0x18002b5cb  lea     r8d, [rsi-1Ch]
0x18002b5cf  call    OneXValidateVariableBlob
0x18002b5d4  mov     ebx, eax
0x18002b5d6  test    eax, eax
0x18002b5d8  jz      short loc_18002B5F7
0x18002b5da  cmp     r11, r12
0x18002b5dd  jz      loc_18002B6B5
0x18002b5e3  test    byte ptr [r11+44h], 1
0x18002b5e8  jz      loc_18002B692
0x18002b5ee  lea     edx, [r9-9]
0x18002b5f2  jmp     loc_18002B522
0x18002b5f7  test    ebp, ebp
0x18002b5f9  jz      loc_18002B692
0x18002b5ff  test    byte ptr [rdi+8], 1
0x18002b603  jnz     short loc_18002B62D
0x18002b605  mov     ebx, 5000Ch
0x18002b60a  cmp     r11, r12
0x18002b60d  jz      loc_18002B6B5
0x18002b613  test    byte ptr [r11+44h], 1
0x18002b618  jz      short loc_18002B692
0x18002b61a  mov     rcx, [r11+38h]
0x18002b61e  mov     edx, 14h
0x18002b623  mov     r8, r13
0x18002b626  call    WPP_SF_
0x18002b62b  jmp     short loc_18002B68B
0x18002b62d  mov     ecx, [rdi+18h]
0x18002b630  add     rcx, rdi; pSid
0x18002b633  call    cs:__imp_IsValidSid
0x18002b639  test    eax, eax
0x18002b63b  jnz     short loc_18002B68B
0x18002b63d  call    cs:__imp_GetLastError
0x18002b643  mov     ebx, eax
0x18002b645  test    eax, eax
0x18002b647  jz      short loc_18002B68B
0x18002b649  mov     r11, cs:WPP_GLOBAL_Control
0x18002b650  cmp     r11, r12
0x18002b653  jz      short loc_18002B6B5
0x18002b655  test    byte ptr [r11+44h], 1
0x18002b65a  jz      short loc_18002B692
0x18002b65c  mov     edx, 15h
0x18002b661  mov     r9d, eax
0x18002b664  jmp     short loc_18002B67F
0x18002b666  mov     ebx, 5000Ch
0x18002b66b  cmp     r11, r12
0x18002b66e  jz      short loc_18002B6B5
0x18002b670  test    byte ptr [r11+44h], 1
0x18002b675  jz      short loc_18002B692
0x18002b677  mov     edx, 12h
0x18002b67c  mov     r9d, ebp
0x18002b67f  mov     rcx, [r11+38h]
0x18002b683  mov     r8, r13
0x18002b686  call    WPP_SF_D
0x18002b68b  mov     r11, cs:WPP_GLOBAL_Control
0x18002b692  cmp     r11, r12
0x18002b695  jz      short loc_18002B6B5
0x18002b697  test    dword ptr [r11+44h], 800h
0x18002b69f  jz      short loc_18002B6B5
0x18002b6a1  mov     rcx, [r11+38h]
0x18002b6a5  mov     edx, 16h
0x18002b6aa  mov     r9d, ebx
0x18002b6ad  mov     r8, r13
0x18002b6b0  call    WPP_SF_D
0x18002b6b5  mov     eax, ebx
0x18002b6b7  add     rsp, 38h
0x18002b6bb  pop     r15
0x18002b6bd  pop     r14
0x18002b6bf  pop     r13
0x18002b6c1  pop     r12
0x18002b6c3  pop     rdi
0x18002b6c4  pop     rsi
0x18002b6c5  pop     rbp
0x18002b6c6  pop     rbx
0x18002b6c7  retn
```
