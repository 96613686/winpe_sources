# CFveApiBase::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)

- ea: `0x18009d0b4`
- end: `0x18009d1c7`
- name: `?IsAssociatedOS@CFveApiBase@@KAJPEAXPEAU_GUID@@1PEAE@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *, struct _GUID *, struct _GUID *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18009ba80`

## callees

- `0x18000ba30`
- `0x180018b10`
- `0x18009befc`
- `0x18009d0b4`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18009d1a3`
- `bcd!BcdCloseObject` at `0x180124914`
- `bcd!BcdCloseObject` at `0x18009d1a3`
- `bcd!BcdCloseObject` at `0x180124914`
- `bcd!BcdOpenObject` at `0x18009d0f4`
- `bcd!BcdOpenObject` at `0x18009d0f4`

## pseudocode

```c
__int64 __fastcall CFveApiBase::IsAssociatedOS(void *a1, struct _GUID *a2, struct _GUID *a3, unsigned __int8 *a4)
{
  int v6; // eax
  int v7; // ebx
  int BcdElementData; // eax
  unsigned int i; // eax
  _QWORD *v10; // r8
  __int64 v11; // rdx
  unsigned int v13; // [rsp+24h] [rbp-44h] BYREF
  void *lpMem; // [rsp+28h] [rbp-40h] BYREF
  unsigned int v15; // [rsp+30h] [rbp-38h]
  void *v16; // [rsp+38h] [rbp-30h] BYREF

  v16 = 0;
  lpMem = 0;
  v13 = 0;
  *a4 = 0;
  v6 = BcdOpenObject(a1, a2, &v16);
  v7 = FromNtStatus(v6);
  if ( v7 >= 0 )
  {
    BcdElementData = CFveApiBase::GetBcdElementData(v16, 0x14000008u, &lpMem, &v13);
    v7 = BcdElementData;
    if ( BcdElementData >= 0 )
    {
      if ( (v13 & 0xF) != 0 )
      {
        v7 = -2147024809;
      }
      else
      {
        for ( i = 0; ; ++i )
        {
          v15 = i;
          if ( i >= v13 >> 4 )
            break;
          v10 = (char *)lpMem + 16 * i;
          v11 = *(_QWORD *)&a3->Data1 - *v10;
          if ( *(_QWORD *)&a3->Data1 == *v10 )
            v11 = *(_QWORD *)a3->Data4 - v10[1];
          if ( !v11 )
          {
            *a4 = 1;
            break;
          }
        }
      }
    }
    else if ( BcdElementData == -2147023728 )
    {
      v7 = 0;
    }
  }
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( v16 )
    BcdCloseObject(v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009d0b4  push    rbx
0x18009d0b6  push    rsi
0x18009d0b7  push    rdi
0x18009d0b8  sub     rsp, 50h
0x18009d0bc  mov     rax, cs:__security_cookie
0x18009d0c3  xor     rax, rsp
0x18009d0c6  mov     [rsp+68h+var_28], rax
0x18009d0cb  mov     rdi, r9
0x18009d0ce  mov     rsi, r8
0x18009d0d1  mov     [rsp+68h+var_30], 0
0x18009d0da  mov     [rsp+68h+lpMem], 0
0x18009d0e3  mov     [rsp+68h+var_44], 0
0x18009d0eb  mov     byte ptr [r9], 0
0x18009d0ef  lea     r8, [rsp+68h+var_30]
0x18009d0f4  call    cs:__imp_BcdOpenObject
0x18009d0fb  nop     dword ptr [rax+rax+00h]
0x18009d100  mov     ecx, eax; int
0x18009d102  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009d107  mov     ebx, eax
0x18009d109  mov     [rsp+68h+var_48], eax
0x18009d10d  test    eax, eax
0x18009d10f  js      short loc_18009D18A
0x18009d111  lea     r9, [rsp+68h+var_44]; unsigned int *
0x18009d116  lea     r8, [rsp+68h+lpMem]; void **
0x18009d11b  mov     edx, 14000008h; unsigned int
0x18009d120  mov     rcx, [rsp+68h+var_30]; void *
0x18009d125  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18009d12a  mov     ebx, eax
0x18009d12c  mov     [rsp+68h+var_48], eax
0x18009d130  test    eax, eax
0x18009d132  jns     short loc_18009D143
0x18009d134  cmp     eax, 80070490h
0x18009d139  jnz     short loc_18009D18A
0x18009d13b  xor     ebx, ebx
0x18009d13d  mov     [rsp+68h+var_48], ebx
0x18009d141  jmp     short loc_18009D18A
0x18009d143  mov     ecx, [rsp+68h+var_44]
0x18009d147  test    cl, 0Fh
0x18009d14a  jz      short loc_18009D153
0x18009d14c  mov     ebx, 80070057h
0x18009d151  jmp     short loc_18009D13D
0x18009d153  shr     ecx, 4
0x18009d156  xor     eax, eax
0x18009d158  mov     [rsp+68h+var_38], eax
0x18009d15c  cmp     eax, ecx
0x18009d15e  jnb     short loc_18009D18A
0x18009d160  mov     r8d, eax
0x18009d163  shl     r8, 4
0x18009d167  add     r8, [rsp+68h+lpMem]
0x18009d16c  mov     rdx, [rsi]
0x18009d16f  sub     rdx, [r8]
0x18009d172  jnz     short loc_18009D17C
0x18009d174  mov     rdx, [rsi+8]
0x18009d178  sub     rdx, [r8+8]
0x18009d17c  test    rdx, rdx
0x18009d17f  jnz     short loc_18009D186
0x18009d181  mov     byte ptr [rdi], 1
0x18009d184  jmp     short loc_18009D18A
0x18009d186  inc     eax
0x18009d188  jmp     short loc_18009D158
0x18009d18a  mov     rcx, [rsp+68h+lpMem]; lpMem
0x18009d18f  test    rcx, rcx
0x18009d192  jz      short loc_18009D199
0x18009d194  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18009d199  mov     rcx, [rsp+68h+var_30]
0x18009d19e  test    rcx, rcx
0x18009d1a1  jz      short loc_18009D1AF
0x18009d1a3  call    cs:__imp_BcdCloseObject
0x18009d1aa  nop     dword ptr [rax+rax+00h]
0x18009d1af  mov     eax, ebx
0x18009d1b1  mov     rcx, [rsp+68h+var_28]
0x18009d1b6  xor     rcx, rsp; StackCookie
0x18009d1b9  call    __security_check_cookie
0x18009d1be  add     rsp, 50h
0x18009d1c2  pop     rdi
0x18009d1c3  pop     rsi
0x18009d1c4  pop     rbx
0x18009d1c5  retn
0x1801248f3  push    rbp
0x1801248f5  sub     rsp, 20h
0x1801248f9  mov     rbp, rdx
0x1801248fc  mov     rcx, [rbp+28h]; lpMem
0x180124900  test    rcx, rcx
0x180124903  jz      short loc_18012490B
0x180124905  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18012490a  nop
0x18012490b  mov     rcx, [rbp+38h]
0x18012490f  test    rcx, rcx
0x180124912  jz      short loc_180124921
0x180124914  call    cs:__imp_BcdCloseObject
0x18012491b  nop     dword ptr [rax+rax+00h]
0x180124920  nop
0x180124921  add     rsp, 20h
0x180124925  pop     rbp
0x180124926  retn
```
