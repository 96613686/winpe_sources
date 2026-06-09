# RegPreSetKeySecurity

- ea: `0x140008524`
- end: `0x140008713`
- name: `RegPreSetKeySecurity`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140033020`

## callees

- `0x140008524`
- `0x140009b80`
- `0x140011650`
- `0x14002b0cc`
- `0x140033978`
- `0x140033bb8`
- `0x14003410c`
- `0x14003588c`
- `0x1400358c0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140008625`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140008625`
- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x1400086b8`
- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x1400086b8`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x1400085a5`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x1400085a5`
- `ntoskrnl!ZwClose` at `0x14000869f`
- `ntoskrnl!ZwClose` at `0x14000869f`

## pseudocode

```c
__int64 __fastcall RegPreSetKeySecurity(_QWORD *a1)
{
  _QWORD *v2; // rbx
  int KeyObjectIDEx; // edi
  PVOID v5; // [rsp+40h] [rbp-30h] BYREF
  PVOID P; // [rsp+48h] [rbp-28h] BYREF
  __int64 v7; // [rsp+50h] [rbp-20h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-18h] BYREF

  v7 = 0;
  v2 = 0;
  v5 = 0;
  P = 0;
  Handle = 0;
  if ( !_bittest64((const signed __int64 *)&xmmword_14001B740, 0x2Cu) )
    return 0;
  if ( !a1 || !a1[1] )
    return 3221225485LL;
  KeyObjectIDEx = CmCallbackGetKeyObjectIDEx((char *)RegData + 8, *a1, 0, &v7, 0);
  if ( KeyObjectIDEx >= 0 && _bittest64((const signed __int64 *)&xmmword_14001B740, 0x2Cu) )
  {
    RegMatchData(v7, 0, 0x400000, &v5);
    if ( v5 )
    {
      v2 = (_QWORD *)MpRegpAllocSetKeySecurityContext();
      if ( v2 )
      {
        KeyObjectIDEx = ObOpenObjectByPointer((PVOID)*a1, 0x200u, 0, 0xF003Fu, 0, 0, &Handle);
        if ( KeyObjectIDEx >= 0 )
        {
          KeyObjectIDEx = SecQuerySecurityObject(Handle, *(_DWORD *)a1[1], &P);
          if ( KeyObjectIDEx >= 0 )
          {
            v2[7] = v5;
            v5 = 0;
            v2[5] = v7;
            v7 = 0;
            v2[6] = P;
            P = 0;
            MpRegpInsertCallContext(v2);
            v2 = 0;
          }
        }
      }
      else
      {
        KeyObjectIDEx = -1073741670;
      }
    }
    else
    {
      KeyObjectIDEx = 0;
    }
  }
  if ( P )
  {
    SecFreePool(P, 0x44536353u);
    P = 0;
  }
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v7 )
    CmCallbackReleaseKeyObjectIDEx();
  if ( v5 )
  {
    RegFreeMatchingInfo(v5);
    v5 = 0;
  }
  if ( v2 )
    MpRegpFreeCallContext(v2);
  return (unsigned int)KeyObjectIDEx;
}

```

## disassembly

```asm
0x140008524  mov     [rsp-18h+arg_8], rbx
0x140008529  mov     [rsp-18h+arg_10], rsi
0x14000852e  mov     [rsp-18h+arg_18], rdi
0x140008533  push    rbp
0x140008534  push    r14
0x140008536  push    r15
0x140008538  mov     rbp, rsp
0x14000853b  sub     rsp, 70h
0x14000853f  mov     rax, cs:__security_cookie
0x140008546  xor     rax, rsp
0x140008549  mov     [rbp+var_10], rax
0x14000854d  xor     r14d, r14d
0x140008550  mov     rsi, rcx
0x140008553  bt      qword ptr cs:xmmword_14001B740, 2Ch ; ','
0x14000855c  mov     [rbp+var_20], r14
0x140008560  mov     ebx, r14d
0x140008563  mov     [rbp+var_30], r14
0x140008567  mov     [rbp+P], r14
0x14000856b  mov     [rbp+var_18], r14
0x14000856f  jb      short loc_140008578
0x140008571  xor     eax, eax
0x140008573  jmp     loc_1400086EC
0x140008578  test    rsi, rsi
0x14000857b  jz      loc_1400086E7
0x140008581  cmp     [rcx+8], r14
0x140008585  jz      loc_1400086E7
0x14000858b  mov     rcx, cs:RegData
0x140008592  lea     r9, [rbp+var_20]
0x140008596  mov     rdx, [rsi]
0x140008599  add     rcx, 8
0x14000859d  xor     r8d, r8d
0x1400085a0  mov     dword ptr [rsp+70h+ObjectType], r14d
0x1400085a5  call    cs:__imp_CmCallbackGetKeyObjectIDEx
0x1400085ac  nop     dword ptr [rax+rax+00h]
0x1400085b1  mov     edi, eax
0x1400085b3  test    eax, eax
0x1400085b5  js      loc_14000867F
0x1400085bb  bt      qword ptr cs:xmmword_14001B740, 2Ch ; ','
0x1400085c4  jnb     loc_14000867F
0x1400085ca  mov     rcx, [rbp+var_20]
0x1400085ce  lea     r9, [rbp+var_30]
0x1400085d2  xor     edx, edx
0x1400085d4  mov     r8d, 400000h
0x1400085da  call    RegMatchData
0x1400085df  cmp     [rbp+var_30], r14
0x1400085e3  jnz     short loc_1400085ED
0x1400085e5  mov     edi, r14d
0x1400085e8  jmp     loc_14000867F
0x1400085ed  call    MpRegpAllocSetKeySecurityContext
0x1400085f2  mov     rbx, rax
0x1400085f5  test    rax, rax
0x1400085f8  jnz     short loc_140008601
0x1400085fa  mov     edi, 0C000009Ah
0x1400085ff  jmp     short loc_14000867F
0x140008601  mov     rcx, [rsi]; Object
0x140008604  lea     rax, [rbp+var_18]
0x140008608  mov     [rsp+70h+Handle], rax; Handle
0x14000860d  mov     r9d, 0F003Fh; DesiredAccess
0x140008613  mov     [rsp+70h+AccessMode], r14b; AccessMode
0x140008618  xor     r8d, r8d; PassedAccessState
0x14000861b  mov     edx, 200h; HandleAttributes
0x140008620  mov     [rsp+70h+ObjectType], r14; ObjectType
0x140008625  call    cs:__imp_ObOpenObjectByPointer
0x14000862c  nop     dword ptr [rax+rax+00h]
0x140008631  mov     edi, eax
0x140008633  test    eax, eax
0x140008635  js      short loc_14000867F
0x140008637  mov     rdx, [rsi+8]
0x14000863b  lea     r8, [rbp+P]
0x14000863f  mov     rcx, [rbp+var_18]; Handle
0x140008643  mov     edx, [rdx]; SecurityInformation
0x140008645  call    SecQuerySecurityObject
0x14000864a  mov     edi, eax
0x14000864c  test    eax, eax
0x14000864e  js      short loc_14000867F
0x140008650  mov     rax, [rbp+var_30]
0x140008654  mov     rcx, rbx
0x140008657  mov     [rbx+38h], rax
0x14000865b  mov     rax, [rbp+var_20]
0x14000865f  mov     [rbp+var_30], r14
0x140008663  mov     [rbx+28h], rax
0x140008667  mov     rax, [rbp+P]
0x14000866b  mov     [rbp+var_20], r14
0x14000866f  mov     [rbx+30h], rax
0x140008673  mov     [rbp+P], r14
0x140008677  call    MpRegpInsertCallContext
0x14000867c  mov     rbx, r14
0x14000867f  mov     rcx, [rbp+P]; P
0x140008683  test    rcx, rcx
0x140008686  jz      short loc_140008696
0x140008688  mov     edx, 44536353h; Tag
0x14000868d  call    SecFreePool
0x140008692  mov     [rbp+P], r14
0x140008696  mov     rcx, [rbp+var_18]; Handle
0x14000869a  test    rcx, rcx
0x14000869d  jz      short loc_1400086AF
0x14000869f  call    cs:__imp_ZwClose
0x1400086a6  nop     dword ptr [rax+rax+00h]
0x1400086ab  mov     [rbp+var_18], r14
0x1400086af  mov     rcx, [rbp+var_20]
0x1400086b3  test    rcx, rcx
0x1400086b6  jz      short loc_1400086C4
0x1400086b8  call    cs:__imp_CmCallbackReleaseKeyObjectIDEx
0x1400086bf  nop     dword ptr [rax+rax+00h]
0x1400086c4  mov     rcx, [rbp+var_30]; P
0x1400086c8  test    rcx, rcx
0x1400086cb  jz      short loc_1400086D6
0x1400086cd  call    RegFreeMatchingInfo
0x1400086d2  mov     [rbp+var_30], r14
0x1400086d6  test    rbx, rbx
0x1400086d9  jz      short loc_1400086E3
0x1400086db  mov     rcx, rbx
0x1400086de  call    MpRegpFreeCallContext
0x1400086e3  mov     eax, edi
0x1400086e5  jmp     short loc_1400086EC
0x1400086e7  mov     eax, 0C000000Dh
0x1400086ec  mov     rcx, [rbp+var_10]
0x1400086f0  xor     rcx, rsp; StackCookie
0x1400086f3  call    __security_check_cookie
0x1400086f8  lea     r11, [rsp+70h+var_s0]
0x1400086fd  mov     rbx, [r11+28h]
0x140008701  mov     rsi, [r11+30h]
0x140008705  mov     rdi, [r11+38h]
0x140008709  mov     rsp, r11
0x14000870c  pop     r15
0x14000870e  pop     r14
0x140008710  pop     rbp
0x140008711  retn
```
