# DeflateInitRecordingTables

- ea: `0x180003930`
- end: `0x180003a4b`
- name: `DeflateInitRecordingTables`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005bf0`
- `0x180006758`

## callees

- `0x180003a60`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall DeflateInitRecordingTables(__int64 a1, _WORD *a2, __int64 a3, _WORD *a4)
{
  _WORD *v6; // rdi
  __int64 i; // rcx
  _DWORD v9[14]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+68h] [rbp-98h]
  __int128 v11; // [rsp+70h] [rbp-90h]
  __int128 v12; // [rsp+80h] [rbp-80h]
  __int128 v13; // [rsp+90h] [rbp-70h]
  __int128 v14; // [rsp+A0h] [rbp-60h]
  _WORD v15[576]; // [rsp+B0h] [rbp-50h] BYREF

  v9[0] = 131074;
  v9[1] = 262147;
  v9[2] = 458755;
  v9[3] = 1441808;
  v9[4] = 3932202;
  v11 = 0;
  v9[5] = 5242980;
  v12 = 0;
  v9[6] = 10354837;
  v13 = 0;
  v9[7] = 13107423;
  v14 = 0;
  v9[8] = 21234044;
  v9[9] = 31261209;
  v9[10] = 49283903;
  v9[11] = 65471695;
  v9[12] = 72090969;
  v9[13] = 109250546;
  v10 = 145230375;
  makeTree(32, 9, v9, a4, a3);
  v6 = v15;
  for ( i = 288; i; --i )
    *v6++ = 1;
  return makeTree(288, 13, v15, a2, a1);
}

```

## disassembly

```asm
0x180003930  push    rbp
0x180003932  push    rbx
0x180003933  push    rsi
0x180003934  push    rdi
0x180003935  lea     rbp, [rsp-448h]
0x18000393d  sub     rsp, 548h
0x180003944  mov     rax, cs:__security_cookie
0x18000394b  xor     rax, rsp
0x18000394e  mov     [rbp+460h+var_30], rax
0x180003955  xorps   xmm0, xmm0
0x180003958  mov     [rsp+560h+var_540], r8
0x18000395d  mov     rsi, rdx
0x180003960  mov     [rsp+560h+var_530], 20002h
0x180003968  mov     rbx, rcx
0x18000396b  mov     [rsp+560h+var_52C], 40003h
0x180003973  lea     r8, [rsp+560h+var_530]
0x180003978  mov     [rsp+560h+var_528], 70003h
0x180003980  mov     edx, 9
0x180003985  mov     [rsp+560h+var_524], 160010h
0x18000398d  mov     ecx, 20h ; ' '
0x180003992  mov     [rsp+560h+var_520], 3C002Ah
0x18000399a  movups  [rsp+560h+var_4F0], xmm0
0x18000399f  mov     [rsp+560h+var_51C], 500064h
0x1800039a7  movups  [rbp+460h+var_4E0], xmm0
0x1800039ab  mov     [rsp+560h+var_518], 9E0095h
0x1800039b3  movups  [rbp+460h+var_4D0], xmm0
0x1800039b7  mov     [rsp+560h+var_514], 0C800DFh
0x1800039bf  movups  [rbp+460h+var_4C0], xmm0
0x1800039c3  mov     [rsp+560h+var_510], 144017Ch
0x1800039cb  mov     [rsp+560h+var_50C], 1DD0219h
0x1800039d3  mov     [rsp+560h+var_508], 2F0033Fh
0x1800039db  mov     [rsp+560h+var_504], 3E704CFh
0x1800039e3  mov     [rsp+560h+var_500], 44C0559h
0x1800039eb  mov     [rsp+560h+var_4FC], 68307F2h
0x1800039f3  mov     [rsp+560h+var_4F8], 8A80A27h
0x1800039fc  call    makeTree
0x180003a01  mov     eax, 1
0x180003a06  mov     [rsp+560h+var_540], rbx
0x180003a0b  movzx   eax, ax
0x180003a0e  lea     rdi, [rbp+460h+var_4B0]
0x180003a12  mov     ecx, 120h
0x180003a17  lea     r8, [rbp+460h+var_4B0]
0x180003a1b  rep stosw
0x180003a1e  mov     ecx, 120h
0x180003a23  mov     r9, rsi
0x180003a26  mov     edx, 0Dh
0x180003a2b  call    makeTree
0x180003a30  mov     rcx, [rbp+460h+var_30]
0x180003a37  xor     rcx, rsp; StackCookie
0x180003a3a  call    __security_check_cookie
0x180003a3f  add     rsp, 548h
0x180003a46  pop     rdi
0x180003a47  pop     rsi
0x180003a48  pop     rbx
0x180003a49  pop     rbp
0x180003a4a  retn
```
