# ShouldDisableAsDeletePending(ushort const *,tagDMACCOUNTLOOKUPTYPE)

- ea: `0x140012388`
- end: `0x1400124a2`
- name: `?ShouldDisableAsDeletePending@@YAHPEBGW4tagDMACCOUNTLOOKUPTYPE@@@Z`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400128d4`
- `0x140013350`

## callees

- `0x14000271f`
- `0x140012388`
- `0x140015690`

## import_xrefs

- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x1400123fd`
- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x1400123fd`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x140012418`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x140012418`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x140012433`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x140012433`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140012458`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140012458`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x1400123dc`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x1400123dc`

## pseudocode

```c
__int64 __fastcall ShouldDisableAsDeletePending(__int64 a1)
{
  unsigned int v2; // ebx
  int AcctInfo; // eax
  _WORD *v5; // [rsp+30h] [rbp-248h] BYREF
  int v6; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v7[508]; // [rsp+44h] [rbp-234h] BYREF

  memset_0(v7, 0, sizeof(v7));
  v2 = 0;
  v5 = 0;
  v6 = 512;
  AcctInfo = OmaDmSetNodeValuePresence(52, &v6, 0xFFFFFFFFLL);
  if ( AcctInfo < 0 )
    goto LABEL_8;
  AcctInfo = OmaDmGetAcctInfo(a1, 1, &v6);
  if ( AcctInfo < 0 )
    goto LABEL_8;
  if ( !(unsigned int)OmaDmIsNodePresent(52, &v6, 0xFFFFFFFFLL)
    || !(unsigned int)OmaDmIsNodeValuePresent(52, &v6, 0xFFFFFFFFLL) )
  {
    return v2;
  }
  AcctInfo = OmaDmGetValueFromStruct(52, &v6, 0xFFFFFFFFLL, &v5, 0);
  if ( AcctInfo < 0 )
  {
LABEL_8:
    if ( AcctInfo == -2147024894 )
      return 1;
  }
  else if ( v5 )
  {
    return *v5 == 0xFFFF;
  }
  return v2;
}

```

## disassembly

```asm
0x140012388  push    rbx
0x14001238a  push    rbp
0x14001238b  push    rsi
0x14001238c  push    rdi
0x14001238d  sub     rsp, 258h
0x140012394  mov     rax, cs:__security_cookie
0x14001239b  xor     rax, rsp
0x14001239e  mov     [rsp+278h+var_38], rax
0x1400123a6  mov     rdi, rcx
0x1400123a9  xor     edx, edx; Val
0x1400123ab  lea     rcx, [rsp+278h+var_234]; void *
0x1400123b0  mov     r8d, 1FCh; Size
0x1400123b6  call    memset_0
0x1400123bb  xor     ebx, ebx
0x1400123bd  mov     [rsp+278h+var_248], 0
0x1400123c6  or      esi, 0FFFFFFFFh
0x1400123c9  mov     [rsp+278h+var_238], 200h
0x1400123d1  mov     r8d, esi
0x1400123d4  lea     rdx, [rsp+278h+var_238]
0x1400123d9  lea     ecx, [rbx+34h]
0x1400123dc  call    cs:__imp_OmaDmSetNodeValuePresence
0x1400123e3  nop     dword ptr [rax+rax+00h]
0x1400123e8  lea     ebp, [rbx+1]
0x1400123eb  test    eax, eax
0x1400123ed  js      loc_14001247B
0x1400123f3  lea     r8, [rsp+278h+var_238]
0x1400123f8  mov     edx, ebp
0x1400123fa  mov     rcx, rdi
0x1400123fd  call    cs:__imp_OmaDmGetAcctInfo
0x140012404  nop     dword ptr [rax+rax+00h]
0x140012409  test    eax, eax
0x14001240b  js      short loc_14001247B
0x14001240d  mov     r8d, esi
0x140012410  lea     rdx, [rsp+278h+var_238]
0x140012415  lea     ecx, [rbx+34h]
0x140012418  call    cs:__imp_OmaDmIsNodePresent
0x14001241f  nop     dword ptr [rax+rax+00h]
0x140012424  test    eax, eax
0x140012426  jz      short loc_140012483
0x140012428  mov     r8d, esi
0x14001242b  lea     rdx, [rsp+278h+var_238]
0x140012430  lea     ecx, [rbx+34h]
0x140012433  call    cs:__imp_OmaDmIsNodeValuePresent
0x14001243a  nop     dword ptr [rax+rax+00h]
0x14001243f  test    eax, eax
0x140012441  jz      short loc_140012483
0x140012443  lea     r9, [rsp+278h+var_248]
0x140012448  mov     [rsp+278h+var_258], rbx
0x14001244d  mov     r8d, esi
0x140012450  lea     rdx, [rsp+278h+var_238]
0x140012455  lea     ecx, [rbx+34h]
0x140012458  call    cs:__imp_OmaDmGetValueFromStruct
0x14001245f  nop     dword ptr [rax+rax+00h]
0x140012464  test    eax, eax
0x140012466  js      short loc_14001247B
0x140012468  mov     rax, [rsp+278h+var_248]
0x14001246d  test    rax, rax
0x140012470  jz      short loc_140012483
0x140012472  cmp     si, [rax]
0x140012475  jnz     short loc_140012483
0x140012477  mov     ebx, ebp
0x140012479  jmp     short loc_140012483
0x14001247b  cmp     eax, 80070002h
0x140012480  cmovz   ebx, ebp
0x140012483  mov     eax, ebx
0x140012485  mov     rcx, [rsp+278h+var_38]
0x14001248d  xor     rcx, rsp; StackCookie
0x140012490  call    __security_check_cookie
0x140012495  add     rsp, 258h
0x14001249c  pop     rdi
0x14001249d  pop     rsi
0x14001249e  pop     rbp
0x14001249f  pop     rbx
0x1400124a0  retn
```
