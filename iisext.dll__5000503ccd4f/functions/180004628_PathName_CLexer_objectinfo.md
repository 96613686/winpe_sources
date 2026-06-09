# PathName(CLexer *,_objectinfo *)

- ea: `0x180004628`
- end: `0x180004788`
- name: `?PathName@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct CLexer *this, struct _objectinfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000449c`

## callees

- `0x180004224`
- `0x180004304`
- `0x180004628`
- `0x1800111e0`

## pseudocode

```c
int __fastcall PathName(struct CLexer *this, struct _objectinfo *a2)
{
  int result; // eax
  unsigned int v5; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v6[3]; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 v7[264]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v8[264]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v9[264]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v10[264]; // [rsp+660h] [rbp+560h] BYREF

  v6[0] = 0;
  while ( 1 )
  {
    v5 = 0;
    result = CLexer::GetNextToken(this, v7, &v5);
    if ( result < 0 )
      break;
    if ( v5 != 1 )
      return -2147463168;
    result = CLexer::GetNextToken(this, v9, &v5);
    if ( result < 0 )
      return result;
    if ( v5 == 25 )
    {
      result = CLexer::GetNextToken(this, v8, &v5);
      if ( result < 0 )
        return result;
      if ( v5 != 1 )
        return -2147463168;
      result = AddComponent(a2, v7, v8);
      if ( result < 0 )
        return result;
    }
    else
    {
      result = AddComponent(a2, v7, 0);
      if ( result < 0 )
        return result;
      if ( *((_DWORD *)this + 5) != 4 )
        *(_QWORD *)this += -2LL * *((unsigned int *)this + 4);
    }
    result = CLexer::GetNextToken(this, v10, v6);
    if ( result < 0 )
      return result;
    if ( v6[0] != 3 && v6[0] != 14 )
    {
      if ( *((_DWORD *)this + 5) != 4 )
        *(_QWORD *)this += -2LL * *((unsigned int *)this + 4);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004628  mov     [rsp-8+arg_10], rbx
0x18000462d  mov     [rsp-8+arg_18], rdi
0x180004632  push    rbp
0x180004633  lea     rbp, [rsp-780h]
0x18000463b  sub     rsp, 880h
0x180004642  mov     rax, cs:__security_cookie
0x180004649  xor     rax, rsp
0x18000464c  mov     [rbp+780h+var_10], rax
0x180004653  mov     rdi, rdx
0x180004656  mov     [rsp+880h+var_85C], 0
0x18000465e  mov     rbx, rcx
0x180004661  lea     r8, [rsp+880h+var_860]; unsigned int *
0x180004666  mov     [rsp+880h+var_860], 0
0x18000466e  lea     rdx, [rsp+880h+var_850]; unsigned __int16 *
0x180004673  mov     rcx, rbx; this
0x180004676  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x18000467b  test    eax, eax
0x18000467d  js      loc_180004732
0x180004683  cmp     [rsp+880h+var_860], 1
0x180004688  jnz     loc_180004781
0x18000468e  lea     r8, [rsp+880h+var_860]; unsigned int *
0x180004693  mov     rcx, rbx; this
0x180004696  lea     rdx, [rbp+780h+var_430]; unsigned __int16 *
0x18000469d  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800046a2  test    eax, eax
0x1800046a4  js      loc_180004732
0x1800046aa  cmp     [rsp+880h+var_860], 19h
0x1800046af  jnz     loc_180004756
0x1800046b5  lea     r8, [rsp+880h+var_860]; unsigned int *
0x1800046ba  mov     rcx, rbx; this
0x1800046bd  lea     rdx, [rbp+780h+var_640]; unsigned __int16 *
0x1800046c4  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800046c9  test    eax, eax
0x1800046cb  js      short loc_180004732
0x1800046cd  cmp     [rsp+880h+var_860], 1
0x1800046d2  jnz     loc_180004781
0x1800046d8  lea     r8, [rbp+780h+var_640]; unsigned __int16 *
0x1800046df  mov     rcx, rdi; struct _objectinfo *
0x1800046e2  lea     rdx, [rsp+880h+var_850]; unsigned __int16 *
0x1800046e7  call    ?AddComponent@@YAJPEAU_objectinfo@@PEAG1@Z; AddComponent(_objectinfo *,ushort *,ushort *)
0x1800046ec  test    eax, eax
0x1800046ee  js      short loc_180004732
0x1800046f0  lea     r8, [rsp+880h+var_85C]; unsigned int *
0x1800046f5  mov     rcx, rbx; this
0x1800046f8  lea     rdx, [rbp+780h+var_220]; unsigned __int16 *
0x1800046ff  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x180004704  test    eax, eax
0x180004706  js      short loc_180004732
0x180004708  cmp     [rsp+880h+var_85C], 3
0x18000470d  jz      loc_180004661
0x180004713  cmp     [rsp+880h+var_85C], 0Eh
0x180004718  jz      loc_180004661
0x18000471e  cmp     dword ptr [rbx+14h], 4
0x180004722  jz      short loc_180004730
0x180004724  mov     eax, [rbx+10h]
0x180004727  neg     rax
0x18000472a  add     rax, rax
0x18000472d  add     [rbx], rax
0x180004730  xor     eax, eax
0x180004732  mov     rcx, [rbp+780h+var_10]
0x180004739  xor     rcx, rsp; StackCookie
0x18000473c  call    __security_check_cookie
0x180004741  lea     r11, [rsp+880h+var_s0]
0x180004749  mov     rbx, [r11+20h]
0x18000474d  mov     rdi, [r11+28h]
0x180004751  mov     rsp, r11
0x180004754  pop     rbp
0x180004755  retn
0x180004756  xor     r8d, r8d; unsigned __int16 *
0x180004759  lea     rdx, [rsp+880h+var_850]; unsigned __int16 *
0x18000475e  mov     rcx, rdi; struct _objectinfo *
0x180004761  call    ?AddComponent@@YAJPEAU_objectinfo@@PEAG1@Z; AddComponent(_objectinfo *,ushort *,ushort *)
0x180004766  test    eax, eax
0x180004768  js      short loc_180004732
0x18000476a  cmp     dword ptr [rbx+14h], 4
0x18000476e  jz      short loc_1800046F0
0x180004770  mov     eax, [rbx+10h]
0x180004773  neg     rax
0x180004776  add     rax, rax
0x180004779  add     [rbx], rax
0x18000477c  jmp     loc_1800046F0
0x180004781  mov     eax, 80005000h
0x180004786  jmp     short loc_180004732
```
