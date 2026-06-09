# WriteThreadInfoList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000eb24`
- end: `0x18000ec68`
- name: `?WriteThreadInfoList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000bcbc`
- `0x18000eb24`
- `0x18001951c`

## pseudocode

```c
__int64 __fastcall WriteThreadInfoList(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  int v6; // eax
  unsigned int v7; // edx
  __int64 result; // rax
  _QWORD **v9; // rsi
  _QWORD *v10; // rdi
  _QWORD *v11; // rcx
  unsigned int v12; // edx
  __int64 v13; // rax
  unsigned int v14; // ecx
  _DWORD v15[4]; // [rsp+20h] [rbp-60h] BYREF
  _DWORD v16[4]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+40h] [rbp-40h]
  __int64 v18; // [rsp+48h] [rbp-38h]
  __int64 v19; // [rsp+50h] [rbp-30h]
  __int64 v20; // [rsp+58h] [rbp-28h]
  __int64 v21; // [rsp+60h] [rbp-20h]
  __int64 v22; // [rsp+68h] [rbp-18h]

  memset_0(v16, 0, 0x40u);
  v6 = *((_DWORD *)a3 + 20);
  if ( v6 )
  {
    v7 = *((_DWORD *)a2 + 15);
    v15[1] = 64;
    v15[0] = 12;
    v15[2] = v6;
    result = WriteAtOffset(a1, v7, v15, 0xCu);
    if ( (_DWORD)result )
      return result;
    *((_DWORD *)a2 + 17) += 12;
    v9 = (_QWORD **)((char *)a3 + 104);
    v10 = *v9;
    while ( v10 != v9 )
    {
      if ( (unsigned int)GenCheckCancel(a1) )
        return 2147943623LL;
      v11 = v10 - 23;
      v10 = (_QWORD *)*v10;
      if ( (v11[22] & 0x40) != 0 )
      {
        v12 = *((_DWORD *)a2 + 17);
        v16[0] = *(_DWORD *)v11;
        v16[1] = *((_DWORD *)v11 + 4);
        v16[2] = *((_DWORD *)v11 + 5);
        v16[3] = *((_DWORD *)v11 + 11);
        v17 = v11[6];
        v18 = v11[7];
        v19 = v11[8];
        v20 = v11[9];
        v21 = v11[10];
        v13 = v11[11];
        v14 = *((_DWORD *)a2 + 15) + *((_DWORD *)a2 + 16);
        v22 = v13;
        if ( v12 + 64 > v14 )
          return 2147942487LL;
        result = WriteAtOffset(a1, v12, v16, 0x40u);
        if ( (_DWORD)result )
          return result;
        *((_DWORD *)a2 + 17) += 64;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000eb24  push    rbp
0x18000eb26  push    rbx
0x18000eb27  push    rsi
0x18000eb28  push    rdi
0x18000eb29  push    r14
0x18000eb2b  mov     rbp, rsp
0x18000eb2e  sub     rsp, 80h
0x18000eb35  mov     rax, cs:__security_cookie
0x18000eb3c  xor     rax, rsp
0x18000eb3f  mov     [rbp+var_10], rax
0x18000eb43  mov     rbx, rdx
0x18000eb46  mov     rsi, r8
0x18000eb49  xor     edx, edx; Val
0x18000eb4b  mov     r14, rcx
0x18000eb4e  lea     rcx, [rbp+var_50]; void *
0x18000eb52  lea     r8d, [rdx+40h]; Size
0x18000eb56  call    memset_0
0x18000eb5b  mov     eax, [rsi+50h]
0x18000eb5e  test    eax, eax
0x18000eb60  jz      loc_18000EC3E
0x18000eb66  mov     edx, [rbx+3Ch]; unsigned int
0x18000eb69  lea     r8, [rbp+var_60]; void *
0x18000eb6d  mov     edi, 0Ch
0x18000eb72  mov     [rbp+var_5C], 40h ; '@'
0x18000eb79  mov     r9d, edi; unsigned int
0x18000eb7c  mov     [rbp+var_60], edi
0x18000eb7f  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18000eb82  mov     [rbp+var_58], eax
0x18000eb85  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000eb8a  test    eax, eax
0x18000eb8c  jnz     loc_18000EC40
0x18000eb92  add     [rbx+44h], edi
0x18000eb95  add     rsi, 68h ; 'h'
0x18000eb99  mov     rdi, [rsi]
0x18000eb9c  jmp     loc_18000EC35
0x18000eba1  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18000eba4  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000eba9  test    eax, eax
0x18000ebab  jnz     loc_18000EC61
0x18000ebb1  lea     rcx, [rdi-0B8h]
0x18000ebb8  mov     rdi, [rdi]
0x18000ebbb  test    byte ptr [rcx+0B0h], 40h
0x18000ebc2  jz      short loc_18000EC35
0x18000ebc4  mov     eax, [rcx]
0x18000ebc6  mov     edx, [rbx+44h]; unsigned int
0x18000ebc9  mov     [rbp+var_50], eax
0x18000ebcc  mov     eax, [rcx+10h]
0x18000ebcf  mov     [rbp+var_4C], eax
0x18000ebd2  mov     eax, [rcx+14h]
0x18000ebd5  mov     [rbp+var_48], eax
0x18000ebd8  mov     eax, [rcx+2Ch]
0x18000ebdb  mov     [rbp+var_44], eax
0x18000ebde  mov     rax, [rcx+30h]
0x18000ebe2  mov     [rbp+var_40], rax
0x18000ebe6  mov     rax, [rcx+38h]
0x18000ebea  mov     [rbp+var_38], rax
0x18000ebee  mov     rax, [rcx+40h]
0x18000ebf2  mov     [rbp+var_30], rax
0x18000ebf6  mov     rax, [rcx+48h]
0x18000ebfa  mov     [rbp+var_28], rax
0x18000ebfe  mov     rax, [rcx+50h]
0x18000ec02  mov     [rbp+var_20], rax
0x18000ec06  mov     rax, [rcx+58h]
0x18000ec0a  mov     ecx, [rbx+40h]
0x18000ec0d  add     ecx, [rbx+3Ch]
0x18000ec10  mov     [rbp+var_18], rax
0x18000ec14  lea     eax, [rdx+40h]
0x18000ec17  cmp     eax, ecx
0x18000ec19  ja      short loc_18000EC5A
0x18000ec1b  mov     r9d, 40h ; '@'; unsigned int
0x18000ec21  lea     r8, [rbp+var_50]; void *
0x18000ec25  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18000ec28  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000ec2d  test    eax, eax
0x18000ec2f  jnz     short loc_18000EC40
0x18000ec31  add     dword ptr [rbx+44h], 40h ; '@'
0x18000ec35  cmp     rdi, rsi
0x18000ec38  jnz     loc_18000EBA1
0x18000ec3e  xor     eax, eax
0x18000ec40  mov     rcx, [rbp+var_10]
0x18000ec44  xor     rcx, rsp; StackCookie
0x18000ec47  call    __security_check_cookie
0x18000ec4c  add     rsp, 80h
0x18000ec53  pop     r14
0x18000ec55  pop     rdi
0x18000ec56  pop     rsi
0x18000ec57  pop     rbx
0x18000ec58  pop     rbp
0x18000ec59  retn
0x18000ec5a  mov     eax, 80070057h
0x18000ec5f  jmp     short loc_18000EC40
0x18000ec61  mov     eax, 800704C7h
0x18000ec66  jmp     short loc_18000EC40
```
