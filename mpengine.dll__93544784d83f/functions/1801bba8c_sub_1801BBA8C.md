# sub_1801BBA8C

- ea: `0x1801bba8c`
- end: `0x1801bc1bb`
- name: `sub_1801BBA8C`
- size: `1839`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x1801a48a4`

## callees

- `0x18001f710`
- `0x18001f740`
- `0x1800789a4`
- `0x18007dfe0`
- `0x18007e05c`
- `0x18007e1f8`
- `0x18013f000`
- `0x18013f020`
- `0x1801655e0`
- `0x180165620`
- `0x1801a1648`
- `0x1801a166c`
- `0x1801a5f5c`
- `0x1801a6064`
- `0x1801aa81c`
- `0x1801b2134`
- `0x1801b7560`
- `0x1801bba8c`
- `0x1801c8638`
- `0x1801ff6a0`
- `0x1802edf80`
- `0x180b74350`
- `0x180b743d0`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x1801bbf75`
- `KERNEL32!InitializeSRWLock` at `0x1801bbfc8`
- `KERNEL32!InitializeSRWLock` at `0x1801bc026`
- `KERNEL32!InitializeSRWLock` at `0x1801bc084`
- `KERNEL32!InitializeSRWLock` at `0x1801bc0c4`
- `KERNEL32!InitializeSRWLock` at `0x1801bbf75`
- `KERNEL32!InitializeSRWLock` at `0x1801bbfc8`
- `KERNEL32!InitializeSRWLock` at `0x1801bc026`
- `KERNEL32!InitializeSRWLock` at `0x1801bc084`
- `KERNEL32!InitializeSRWLock` at `0x1801bc0c4`
- `KERNEL32!GetTempPathW` at `0x1801bbd1b`
- `KERNEL32!GetTempPathW` at `0x1801bbd1b`
- `KERNEL32!GetCurrentDirectoryW` at `0x1801bbc8d`
- `KERNEL32!GetCurrentDirectoryW` at `0x1801bbc8d`
- `KERNEL32!GetLastError` at `0x1801bbd42`
- `KERNEL32!GetLastError` at `0x1801bbd42`

## string_xrefs

- `0x1801bbb2f`: `MpEngineLoad, Path="%ls", KernelTable=%p`

## pseudocode

```c
__int64 __fastcall sub_1801BBA8C(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // r8
  unsigned int v5; // edi
  unsigned __int64 v6; // rdi
  __int64 v7; // r8
  char *v8; // rax
  __int64 v9; // rax
  _WORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rsi
  __int16 v13; // ax
  WCHAR *v14; // rax
  DWORD CurrentDirectoryW; // eax
  char *v16; // rcx
  __int64 v17; // r8
  int v18; // edx
  signed __int64 v19; // r9
  __int16 v20; // ax
  __int64 v21; // rcx
  DWORD LastError; // eax
  void (__fastcall ***v23)(_QWORD, __int64); // rcx
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  void (__fastcall ***v26)(_QWORD, __int64); // rcx
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  void *v28; // rsi
  void *v29; // r14
  int v31; // eax
  RTL_SRWLOCK *v32; // rax
  RTL_SRWLOCK *v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  RTL_SRWLOCK *v36; // rax
  RTL_SRWLOCK *v37; // rcx
  RTL_SRWLOCK *v38; // rax
  RTL_SRWLOCK *v39; // rcx
  RTL_SRWLOCK *v40; // rax
  RTL_SRWLOCK *v41; // rcx
  __int64 v42; // rdi
  void *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // [rsp+30h] [rbp-488h]
  char v47; // [rsp+48h] [rbp-470h] BYREF
  const wchar_t *v48; // [rsp+58h] [rbp-460h]
  __int64 v49; // [rsp+60h] [rbp-458h]
  char v50; // [rsp+68h] [rbp-450h] BYREF
  _WORD *v51; // [rsp+78h] [rbp-440h]
  int v52; // [rsp+80h] [rbp-438h]
  int v53; // [rsp+84h] [rbp-434h]
  _WORD v54[512]; // [rsp+90h] [rbp-428h] BYREF

  v4 = (_QWORD *)sub_180165620(1, 89120);
  qword_18105B1D0 = v4;
  if ( !v4 )
    return 32775;
  *(_QWORD *)qword_18105B1D0 = &sub_1801BE640;
  v6 = -1;
  v4[10887] = -1;
  if ( dword_18100F574 && (unsigned __int8)(byte_18100F578 - 1) > 2u || byte_18105B1F4 )
  {
    if ( (int)sub_1801A5F5C(v54, 512, L"MpEngineLoad, Path=\"%ls\", KernelTable=%p", a1, qword_18105B1D0) >= 0 )
    {
      if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v54[v9] );
        v51 = v54;
        v52 = 2 * v9 + 2;
        v53 = 0;
        v8 = &v50;
        goto LABEL_15;
      }
    }
    else if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
    {
      v48 = L"String too long";
      v49 = 32;
      v8 = &v47;
LABEL_15:
      sub_1801A6064(&qword_18100F550, qword_180C18850, v7, 2, v8);
    }
  }
  *a2 = &sub_1801BE640;
  do
    ++v6;
  while ( *(_WORD *)(a1 + 2 * v6) );
  if ( v6 + 2 < v6 || v6 + 2 > 0x104 )
  {
LABEL_46:
    v5 = 32780;
    goto LABEL_47;
  }
  v10 = (char *)qword_18105B1D0 + 56;
  v11 = 260;
  v12 = a1 - ((_QWORD)qword_18105B1D0 + 56);
  while ( v11 != -2147483386 )
  {
    v13 = *(_WORD *)((char *)v10 + v12);
    if ( v13 )
    {
      *v10++ = v13;
      if ( --v11 )
        continue;
    }
    if ( !v11 )
      --v10;
    break;
  }
  *v10 = 0;
  if ( v6 && *((_WORD *)qword_18105B1D0 + v6 + 27) != 47 && *((_WORD *)qword_18105B1D0 + v6 + 27) != 92 )
    *((_WORD *)qword_18105B1D0 + v6++ + 28) = 92;
  v14 = (WCHAR *)qword_18105B1D0;
  *((_WORD *)qword_18105B1D0 + v6 + 28) = 0;
  CurrentDirectoryW = GetCurrentDirectoryW(0x104u, v14 + 852);
  v16 = (char *)qword_18105B1D0 + 1704;
  if ( CurrentDirectoryW )
  {
    v18 = sub_1801B7560(v16, 260, &word_180C1BB88);
  }
  else
  {
    v17 = 260;
    v18 = 0;
    v19 = (char *)L".\\" - v16;
    while ( v17 != -2147483386 )
    {
      v20 = *(_WORD *)&v16[v19];
      if ( v20 )
      {
        *(_WORD *)v16 = v20;
        v16 += 2;
        if ( --v17 )
          continue;
      }
      if ( !v17 )
      {
        v16 -= 2;
        v18 = -2147024774;
      }
      break;
    }
    *(_WORD *)v16 = 0;
  }
  if ( v18 < 0 )
  {
    v21 = (unsigned int)v18;
LABEL_41:
    v5 = sub_1801B2134(v21);
    goto LABEL_47;
  }
  if ( !GetTempPathW(0x104u, (LPWSTR)qword_18105B1D0 + 288) )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      sub_1801A166C(*((_QWORD *)hDevice + 2), 326, &stru_180C1BC18, LastError);
    }
    goto LABEL_46;
  }
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
    sub_1801C8638(*((_QWORD *)hDevice + 2), 327, &stru_180C1BC18, (char *)qword_18105B1D0 + 576);
  v31 = sub_1802EDF80((char *)qword_18105B1D0 + 8);
  if ( v31 < 0 )
  {
    v21 = (unsigned int)v31;
    goto LABEL_41;
  }
  v32 = (RTL_SRWLOCK *)sub_18001F740(16, qword_180BE0980);
  v33 = v32;
  if ( v32 )
    v32->Ptr = &mrmw_t::`vftable';
  else
    v33 = 0;
  *((_QWORD *)qword_18105B1D0 + 2) = v33;
  if ( !v33 )
  {
    v34 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_77;
    v35 = 328;
LABEL_76:
    sub_1801A1648(v34[2], v35, &stru_180C1BC18);
LABEL_77:
    v5 = 32775;
LABEL_47:
    if ( qword_18105B1D0 )
    {
      v23 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)qword_18105B1D0 + 1);
      if ( v23 )
        (**v23)(v23, 1);
      v24 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)qword_18105B1D0 + 3);
      if ( v24 )
        (**v24)(v24, 1);
      v25 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)qword_18105B1D0 + 4);
      if ( v25 )
        (**v25)(v25, 1);
      v26 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)qword_18105B1D0 + 2);
      if ( v26 )
        (**v26)(v26, 1);
      v27 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)qword_18105B1D0 + 5);
      if ( v27 )
        (**v27)(v27, 1);
      v28 = (void *)*((_QWORD *)qword_18105B1D0 + 11122);
      if ( v28 )
      {
        sub_1801AA81C(*((_QWORD *)qword_18105B1D0 + 11122));
        sub_18013F020(v28);
      }
      v29 = (void *)*((_QWORD *)qword_18105B1D0 + 6);
      if ( v29 )
      {
        sub_18007E05C(*((_QWORD *)qword_18105B1D0 + 6));
        sub_18013F020(v29);
      }
      sub_1801655E0(qword_18105B1D0);
      qword_18105B1D0 = 0;
    }
    return v5;
  }
  InitializeSRWLock(v33 + 1);
  v36 = (RTL_SRWLOCK *)sub_18001F740(16, qword_180BE0980);
  v37 = v36;
  if ( v36 )
    v36->Ptr = &mrmw_t::`vftable';
  else
    v37 = 0;
  *((_QWORD *)qword_18105B1D0 + 3) = v37;
  if ( !v37 )
  {
    v34 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_77;
    v35 = 329;
    goto LABEL_76;
  }
  InitializeSRWLock(v37 + 1);
  v38 = (RTL_SRWLOCK *)sub_18001F740(16, qword_180BE0980);
  v39 = v38;
  if ( v38 )
    v38->Ptr = &mrmw_t::`vftable';
  else
    v39 = 0;
  *((_QWORD *)qword_18105B1D0 + 4) = v39;
  if ( !v39 )
  {
    v34 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_77;
    v35 = 330;
    goto LABEL_76;
  }
  InitializeSRWLock(v39 + 1);
  v40 = (RTL_SRWLOCK *)sub_18001F740(16, qword_180BE0980);
  v41 = v40;
  if ( v40 )
    v40->Ptr = &mrmw_t::`vftable';
  else
    v41 = 0;
  *((_QWORD *)qword_18105B1D0 + 5) = v41;
  if ( !v41 )
  {
    v34 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_77;
    v35 = 331;
    goto LABEL_76;
  }
  InitializeSRWLock(v41 + 1);
  sub_180B743D0(&qword_181042B90, 0, 80);
  v42 = sub_18001F710(32);
  *(_OWORD *)v42 = 0;
  *(_OWORD *)(v42 + 16) = 0;
  *(_BYTE *)v42 = 1;
  *(_QWORD *)(v42 + 16) = &mrmw_t::`vftable';
  InitializeSRWLock((PSRWLOCK)(v42 + 24));
  v43 = *(void **)(v42 + 8);
  if ( v43 )
  {
    sub_1801FF6A0(v43);
    *(_QWORD *)(v42 + 8) = 0;
  }
  *((_QWORD *)qword_18105B1D0 + 11122) = v42;
  v46 = sub_18001F710(72);
  sub_180B743D0(v46, 0, 72);
  v44 = sub_18007DFE0(v46);
  *((_QWORD *)qword_18105B1D0 + 6) = v44;
  v45 = sub_18007E1F8(v44);
  if ( v45 < 0 )
    sub_1800789A4((unsigned int)v45);
  return 0;
}

```

## disassembly

```asm
0x1801bba8c  mov     [rsp+arg_10], rbx
0x1801bba91  mov     [rsp+arg_18], rsi
0x1801bba96  push    rdi
0x1801bba97  push    r14
0x1801bba99  push    r15
0x1801bba9b  sub     rsp, 4A0h
0x1801bbaa2  mov     rax, cs:__security_cookie
0x1801bbaa9  xor     rax, rsp
0x1801bbaac  mov     [rsp+4B8h+var_28], rax
0x1801bbab4  mov     r14, rdx
0x1801bbab7  mov     rsi, rcx
0x1801bbaba  mov     edx, 15C20h
0x1801bbabf  mov     ecx, 1
0x1801bbac4  call    sub_180165620
0x1801bbac9  mov     r8, rax
0x1801bbacc  mov     cs:qword_18105B1D0, rax
0x1801bbad3  xor     ebx, ebx
0x1801bbad5  test    rax, rax
0x1801bbad8  jnz     short loc_1801BBAE4
0x1801bbada  mov     edi, 8007h
0x1801bbadf  jmp     loc_1801BBE7A
0x1801bbae4  lea     r15, sub_1801BE640
0x1801bbaeb  mov     rax, cs:qword_18105B1D0
0x1801bbaf2  mov     [rax], r15
0x1801bbaf5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801bbaf9  mov     [r8+15438h], rdi
0x1801bbb00  cmp     cs:dword_18100F574, ebx
0x1801bbb06  jz      short loc_1801BBB14
0x1801bbb08  mov     al, cs:byte_18100F578
0x1801bbb0e  dec     al
0x1801bbb10  cmp     al, 2
0x1801bbb12  ja      short loc_1801BBB20
0x1801bbb14  cmp     cs:byte_18105B1F4, bl
0x1801bbb1a  jz      loc_1801BBBE7
0x1801bbb20  mov     rax, cs:qword_18105B1D0
0x1801bbb27  mov     [rsp+4B8h+var_498], rax
0x1801bbb2c  mov     r9, rsi
0x1801bbb2f  lea     r8, aMpengineloadPa; "MpEngineLoad, Path=\"%ls\", KernelTable"...
0x1801bbb36  mov     edx, 200h
0x1801bbb3b  lea     rcx, [rsp+4B8h+var_428]
0x1801bbb43  call    sub_1801A5F5C
0x1801bbb48  test    eax, eax
0x1801bbb4a  jns     short loc_1801BBB7D
0x1801bbb4c  test    byte ptr cs:dword_181042B40, 1
0x1801bbb53  jnz     short loc_1801BBB61
0x1801bbb55  cmp     cs:byte_18105B1F4, bl
0x1801bbb5b  jz      loc_1801BBBE7
0x1801bbb61  lea     rax, aStringTooLong_0; "String too long"
0x1801bbb68  mov     [rsp+4B8h+var_460], rax
0x1801bbb6d  mov     [rsp+4B8h+var_458], 20h ; ' '
0x1801bbb76  lea     rax, [rsp+4B8h+var_470]
0x1801bbb7b  jmp     short loc_1801BBBC9
0x1801bbb7d  test    byte ptr cs:dword_181042B40, 1
0x1801bbb84  jnz     short loc_1801BBB8E
0x1801bbb86  cmp     cs:byte_18105B1F4, bl
0x1801bbb8c  jz      short loc_1801BBBE7
0x1801bbb8e  lea     rcx, [rsp+4B8h+var_428]
0x1801bbb96  mov     rax, rdi
0x1801bbb99  inc     rax
0x1801bbb9c  cmp     [rcx+rax*2], bx
0x1801bbba0  jnz     short loc_1801BBB99
0x1801bbba2  lea     eax, ds:2[rax*2]
0x1801bbba9  lea     rcx, [rsp+4B8h+var_428]
0x1801bbbb1  mov     [rsp+4B8h+var_440], rcx
0x1801bbbb6  mov     [rsp+4B8h+var_438], eax
0x1801bbbbd  mov     [rsp+4B8h+var_434], ebx
0x1801bbbc4  lea     rax, [rsp+4B8h+var_450]
0x1801bbbc9  mov     [rsp+4B8h+var_498], rax
0x1801bbbce  mov     r9d, 2
0x1801bbbd4  lea     rdx, qword_180C18850
0x1801bbbdb  lea     rcx, qword_18100F550
0x1801bbbe2  call    sub_1801A6064
0x1801bbbe7  mov     [r14], r15
0x1801bbbea  inc     rdi
0x1801bbbed  cmp     [rsi+rdi*2], bx
0x1801bbbf1  jnz     short loc_1801BBBEA
0x1801bbbf3  lea     rax, [rdi+2]
0x1801bbbf7  cmp     rax, rdi
0x1801bbbfa  jb      loc_1801BBD67
0x1801bbc00  mov     r14d, 104h
0x1801bbc06  cmp     rax, r14
0x1801bbc09  ja      loc_1801BBD67
0x1801bbc0f  mov     rcx, cs:qword_18105B1D0
0x1801bbc16  add     rcx, 38h ; '8'
0x1801bbc1a  mov     edx, r14d
0x1801bbc1d  sub     rsi, rcx
0x1801bbc20  lea     rax, [rdx+7FFFFEFAh]
0x1801bbc27  test    rax, rax
0x1801bbc2a  jz      short loc_1801BBC4B
0x1801bbc2c  movzx   eax, word ptr [rcx+rsi]
0x1801bbc30  test    ax, ax
0x1801bbc33  jz      short loc_1801BBC42
0x1801bbc35  mov     [rcx], ax
0x1801bbc38  add     rcx, 2
0x1801bbc3c  sub     rdx, 1
0x1801bbc40  jnz     short loc_1801BBC20
0x1801bbc42  test    rdx, rdx
0x1801bbc45  jnz     short loc_1801BBC4B
0x1801bbc47  sub     rcx, 2
0x1801bbc4b  mov     [rcx], bx
0x1801bbc4e  cmp     rdi, 1
0x1801bbc52  jb      short loc_1801BBC77
0x1801bbc54  mov     rax, cs:qword_18105B1D0
0x1801bbc5b  cmp     word ptr [rax+rdi*2+36h], 2Fh ; '/'
0x1801bbc61  jz      short loc_1801BBC77
0x1801bbc63  mov     ecx, 5Ch ; '\'
0x1801bbc68  cmp     [rax+rdi*2+36h], cx
0x1801bbc6d  jz      short loc_1801BBC77
0x1801bbc6f  mov     [rax+rdi*2+38h], cx
0x1801bbc74  inc     rdi
0x1801bbc77  mov     rax, cs:qword_18105B1D0
0x1801bbc7e  mov     [rax+rdi*2+38h], bx
0x1801bbc83  lea     rdx, [rax+6A8h]; lpBuffer
0x1801bbc8a  mov     ecx, r14d; nBufferLength
0x1801bbc8d  call    cs:GetCurrentDirectoryW
0x1801bbc93  mov     rcx, cs:qword_18105B1D0
0x1801bbc9a  add     rcx, 6A8h
0x1801bbca1  test    eax, eax
0x1801bbca3  jnz     short loc_1801BBCEA
0x1801bbca5  mov     r8, r14
0x1801bbca8  mov     edx, ebx
0x1801bbcaa  lea     r9, asc_180C1E4B4; ".\\"
0x1801bbcb1  sub     r9, rcx
0x1801bbcb4  lea     rax, [r8+7FFFFEFAh]
0x1801bbcbb  test    rax, rax
0x1801bbcbe  jz      short loc_1801BBCE5
0x1801bbcc0  movzx   eax, word ptr [r9+rcx]
0x1801bbcc5  test    ax, ax
0x1801bbcc8  jz      short loc_1801BBCD7
0x1801bbcca  mov     [rcx], ax
0x1801bbccd  add     rcx, 2
0x1801bbcd1  sub     r8, 1
0x1801bbcd5  jnz     short loc_1801BBCB4
0x1801bbcd7  test    r8, r8
0x1801bbcda  jnz     short loc_1801BBCE5
0x1801bbcdc  sub     rcx, 2
0x1801bbce0  mov     edx, 8007007Ah
0x1801bbce5  mov     [rcx], bx
0x1801bbce8  jmp     short loc_1801BBCFB
0x1801bbcea  lea     r8, word_180C1BB88
0x1801bbcf1  mov     rdx, r14
0x1801bbcf4  call    sub_1801B7560
0x1801bbcf9  mov     edx, eax
0x1801bbcfb  test    edx, edx
0x1801bbcfd  jns     short loc_1801BBD0A
0x1801bbcff  mov     ecx, edx
0x1801bbd01  call    sub_1801B2134
0x1801bbd06  mov     edi, eax
0x1801bbd08  jmp     short loc_1801BBD6C
0x1801bbd0a  mov     rdx, cs:qword_18105B1D0
0x1801bbd11  add     rdx, 240h; lpBuffer
0x1801bbd18  mov     ecx, r14d; nBufferLength
0x1801bbd1b  call    cs:__imp_GetTempPathW
0x1801bbd21  test    eax, eax
0x1801bbd23  jnz     loc_1801BBEA5
0x1801bbd29  lea     rdi, hDevice
0x1801bbd30  mov     rax, cs:hDevice
0x1801bbd37  cmp     rax, rdi
0x1801bbd3a  jz      short loc_1801BBD67
0x1801bbd3c  test    byte ptr [rax+1Ch], 1
0x1801bbd40  jz      short loc_1801BBD67
0x1801bbd42  call    cs:__imp_GetLastError
0x1801bbd48  mov     edx, 146h
0x1801bbd4d  mov     r9d, eax
0x1801bbd50  lea     r8, stru_180C1BC18
0x1801bbd57  mov     rcx, cs:hDevice
0x1801bbd5e  mov     rcx, [rcx+10h]
0x1801bbd62  call    sub_1801A166C
0x1801bbd67  mov     edi, 800Ch
0x1801bbd6c  mov     rax, cs:qword_18105B1D0
0x1801bbd73  test    rax, rax
0x1801bbd76  jz      loc_1801BBE7A
0x1801bbd7c  mov     rcx, [rax+8]
0x1801bbd80  test    rcx, rcx
0x1801bbd83  jz      short loc_1801BBD96
0x1801bbd85  mov     rax, [rcx]
0x1801bbd88  mov     edx, 1
0x1801bbd8d  mov     rax, [rax]
0x1801bbd90  call    cs:__guard_dispatch_icall_fptr
0x1801bbd96  mov     rax, cs:qword_18105B1D0
0x1801bbd9d  mov     rcx, [rax+18h]
0x1801bbda1  test    rcx, rcx
0x1801bbda4  jz      short loc_1801BBDB7
0x1801bbda6  mov     rax, [rcx]
0x1801bbda9  mov     edx, 1
0x1801bbdae  mov     rax, [rax]
0x1801bbdb1  call    cs:__guard_dispatch_icall_fptr
0x1801bbdb7  mov     rax, cs:qword_18105B1D0
0x1801bbdbe  mov     rcx, [rax+20h]
0x1801bbdc2  test    rcx, rcx
0x1801bbdc5  jz      short loc_1801BBDD8
0x1801bbdc7  mov     rax, [rcx]
0x1801bbdca  mov     edx, 1
0x1801bbdcf  mov     rax, [rax]
0x1801bbdd2  call    cs:__guard_dispatch_icall_fptr
0x1801bbdd8  mov     rax, cs:qword_18105B1D0
0x1801bbddf  mov     rcx, [rax+10h]
0x1801bbde3  test    rcx, rcx
0x1801bbde6  jz      short loc_1801BBDF9
0x1801bbde8  mov     rax, [rcx]
0x1801bbdeb  mov     edx, 1
0x1801bbdf0  mov     rax, [rax]
0x1801bbdf3  call    cs:__guard_dispatch_icall_fptr
0x1801bbdf9  mov     rax, cs:qword_18105B1D0
0x1801bbe00  mov     rcx, [rax+28h]
0x1801bbe04  test    rcx, rcx
0x1801bbe07  jz      short loc_1801BBE1A
0x1801bbe09  mov     rax, [rcx]
0x1801bbe0c  mov     edx, 1
0x1801bbe11  mov     rax, [rax]
0x1801bbe14  call    cs:__guard_dispatch_icall_fptr
0x1801bbe1a  mov     rax, cs:qword_18105B1D0
0x1801bbe21  mov     rsi, [rax+15B90h]
0x1801bbe28  test    rsi, rsi
0x1801bbe2b  jz      short loc_1801BBE42
0x1801bbe2d  mov     rcx, rsi
0x1801bbe30  call    sub_1801AA81C
0x1801bbe35  mov     edx, 20h ; ' '
0x1801bbe3a  mov     rcx, rsi; lpMem
0x1801bbe3d  call    sub_18013F020
0x1801bbe42  mov     rax, cs:qword_18105B1D0
0x1801bbe49  mov     r14, [rax+30h]
0x1801bbe4d  test    r14, r14
0x1801bbe50  jz      short loc_1801BBE67
0x1801bbe52  mov     rcx, r14
0x1801bbe55  call    sub_18007E05C
0x1801bbe5a  mov     edx, 48h ; 'H'
0x1801bbe5f  mov     rcx, r14; lpMem
0x1801bbe62  call    sub_18013F020
0x1801bbe67  mov     rcx, cs:qword_18105B1D0; lpMem
0x1801bbe6e  call    sub_1801655E0
0x1801bbe73  mov     cs:qword_18105B1D0, rbx
0x1801bbe7a  mov     eax, edi
0x1801bbe7c  mov     rcx, [rsp+4B8h+var_28]
0x1801bbe84  xor     rcx, rsp; StackCookie
0x1801bbe87  call    __security_check_cookie
0x1801bbe8c  lea     r11, [rsp+4B8h+var_18]
0x1801bbe94  mov     rbx, [r11+30h]
0x1801bbe98  mov     rsi, [r11+38h]
0x1801bbe9c  mov     rsp, r11
0x1801bbe9f  pop     r15
0x1801bbea1  pop     r14
0x1801bbea3  pop     rdi
0x1801bbea4  retn
0x1801bbea5  lea     rdi, hDevice
0x1801bbeac  mov     rcx, cs:hDevice
0x1801bbeb3  cmp     rcx, rdi
0x1801bbeb6  jz      short loc_1801BBEE1
0x1801bbeb8  test    byte ptr [rcx+1Ch], 8
0x1801bbebc  jz      short loc_1801BBEE1
0x1801bbebe  mov     r9, cs:qword_18105B1D0
0x1801bbec5  add     r9, 240h
0x1801bbecc  mov     edx, 147h
0x1801bbed1  lea     r8, stru_180C1BC18
0x1801bbed8  mov     rcx, [rcx+10h]
0x1801bbedc  call    sub_1801C8638
0x1801bbee1  mov     rcx, cs:qword_18105B1D0
0x1801bbee8  add     rcx, 8
0x1801bbeec  call    sub_1802EDF80
0x1801bbef1  test    eax, eax
0x1801bbef3  jns     short loc_1801BBEFC
0x1801bbef5  mov     ecx, eax
0x1801bbef7  jmp     loc_1801BBD01
0x1801bbefc  lea     r14, qword_180BE0980
0x1801bbf03  mov     rdx, r14
0x1801bbf06  mov     r15d, 10h
0x1801bbf0c  mov     ecx, r15d
0x1801bbf0f  call    sub_18001F740
0x1801bbf14  mov     rcx, rax
0x1801bbf17  mov     [rsp+4B8h+var_488], rax
0x1801bbf1c  lea     rsi, ??_7mrmw_t@@6B@; const mrmw_t::`vftable'
0x1801bbf23  test    rax, rax
0x1801bbf26  jz      short loc_1801BBF2D
0x1801bbf28  mov     [rax], rsi
0x1801bbf2b  jmp     short loc_1801BBF30
0x1801bbf2d  mov     rcx, rbx
0x1801bbf30  mov     rax, cs:qword_18105B1D0
0x1801bbf37  mov     [rax+10h], rcx
0x1801bbf3b  test    rcx, rcx
0x1801bbf3e  jnz     short loc_1801BBF71
0x1801bbf40  mov     rcx, cs:hDevice
0x1801bbf47  cmp     rcx, rdi
0x1801bbf4a  jz      short loc_1801BBF67
0x1801bbf4c  test    byte ptr [rcx+1Ch], 1
0x1801bbf50  jz      short loc_1801BBF67
0x1801bbf52  mov     edx, 148h
0x1801bbf57  lea     r8, stru_180C1BC18
0x1801bbf5e  mov     rcx, [rcx+10h]
0x1801bbf62  call    sub_1801A1648
0x1801bbf67  mov     edi, 8007h
0x1801bbf6c  jmp     loc_1801BBD6C
0x1801bbf71  add     rcx, 8; SRWLock
0x1801bbf75  call    cs:InitializeSRWLock
0x1801bbf7b  mov     rdx, r14
0x1801bbf7e  mov     rcx, r15
0x1801bbf81  call    sub_18001F740
0x1801bbf86  mov     rcx, rax
0x1801bbf89  mov     [rsp+4B8h+var_488], rax
0x1801bbf8e  test    rax, rax
0x1801bbf91  jz      short loc_1801BBF98
  ... truncated ...
```
