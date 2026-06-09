# FveBcdUtil::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)

- ea: `0x1800dadec`
- end: `0x1800daef6`
- name: `?IsAssociatedOS@FveBcdUtil@@SAJPEAXPEAU_GUID@@1PEAE@Z`
- size: `266`
- prototype: `__int64 __fastcall(void *, struct _GUID *, struct _GUID *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800da860`

## callees

- `0x180018b10`
- `0x1800dabb8`
- `0x1800dadec`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800daec1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128b81`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800daec1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128b81`
- `bcd!BcdCloseObject` at `0x1800daed7`
- `bcd!BcdCloseObject` at `0x180128b97`
- `bcd!BcdCloseObject` at `0x1800daed7`
- `bcd!BcdCloseObject` at `0x180128b97`
- `bcd!BcdOpenObject` at `0x1800dae21`
- `bcd!BcdOpenObject` at `0x1800dae21`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::IsAssociatedOS(void *a1, struct _GUID *a2, struct _GUID *a3, unsigned __int8 *a4)
{
  int v6; // eax
  int v7; // ebx
  int BcdElementData; // eax
  unsigned int i; // eax
  _QWORD *v10; // r8
  __int64 v11; // rdx
  void *v13; // [rsp+28h] [rbp-20h] BYREF
  void *v14; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  v15 = 0;
  *a4 = 0;
  v6 = BcdOpenObject(a1, a2, &v14);
  v7 = FromNtStatus(v6);
  if ( v7 >= 0 )
  {
    BcdElementData = FveBcdUtil::GetBcdElementData(v14, 0x14000008u, &v13, &v15);
    v7 = BcdElementData;
    if ( BcdElementData >= 0 )
    {
      if ( (v15 & 0xF) != 0 )
      {
        v7 = -2147024809;
      }
      else
      {
        for ( i = 0; i < v15 >> 4; ++i )
        {
          v10 = (char *)v13 + 16 * i;
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
  if ( v13 )
    operator delete(v13);
  if ( v14 )
    BcdCloseObject(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800dadec  mov     rax, rsp
0x1800dadef  mov     [rax+8], rbx
0x1800dadf3  mov     [rax+10h], rsi
0x1800dadf7  push    rdi
0x1800dadf8  sub     rsp, 40h
0x1800dadfc  mov     rdi, r9
0x1800dadff  mov     rsi, r8
0x1800dae02  mov     qword ptr [rax-18h], 0
0x1800dae0a  mov     qword ptr [rax-20h], 0
0x1800dae12  mov     dword ptr [rax+20h], 0
0x1800dae19  mov     byte ptr [r9], 0
0x1800dae1d  lea     r8, [rax-18h]
0x1800dae21  call    cs:__imp_BcdOpenObject
0x1800dae28  nop     dword ptr [rax+rax+00h]
0x1800dae2d  mov     ecx, eax; int
0x1800dae2f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800dae34  mov     ebx, eax
0x1800dae36  mov     [rsp+48h+var_28], eax
0x1800dae3a  test    eax, eax
0x1800dae3c  js      short loc_1800DAEB7
0x1800dae3e  lea     r9, [rsp+48h+arg_18]; unsigned int *
0x1800dae43  lea     r8, [rsp+48h+var_20]; void **
0x1800dae48  mov     edx, 14000008h; unsigned int
0x1800dae4d  mov     rcx, [rsp+48h+var_18]; void *
0x1800dae52  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800dae57  mov     ebx, eax
0x1800dae59  mov     [rsp+48h+var_28], eax
0x1800dae5d  test    eax, eax
0x1800dae5f  jns     short loc_1800DAE70
0x1800dae61  cmp     eax, 80070490h
0x1800dae66  jnz     short loc_1800DAEB7
0x1800dae68  xor     ebx, ebx
0x1800dae6a  mov     [rsp+48h+var_28], ebx
0x1800dae6e  jmp     short loc_1800DAEB7
0x1800dae70  mov     ecx, [rsp+48h+arg_18]
0x1800dae74  test    cl, 0Fh
0x1800dae77  jz      short loc_1800DAE80
0x1800dae79  mov     ebx, 80070057h
0x1800dae7e  jmp     short loc_1800DAE6A
0x1800dae80  shr     ecx, 4
0x1800dae83  xor     eax, eax
0x1800dae85  mov     [rsp+48h+var_24], eax
0x1800dae89  cmp     eax, ecx
0x1800dae8b  jnb     short loc_1800DAEB7
0x1800dae8d  mov     r8d, eax
0x1800dae90  shl     r8, 4
0x1800dae94  add     r8, [rsp+48h+var_20]
0x1800dae99  mov     rdx, [rsi]
0x1800dae9c  sub     rdx, [r8]
0x1800dae9f  jnz     short loc_1800DAEA9
0x1800daea1  mov     rdx, [rsi+8]
0x1800daea5  sub     rdx, [r8+8]
0x1800daea9  test    rdx, rdx
0x1800daeac  jnz     short loc_1800DAEB3
0x1800daeae  mov     byte ptr [rdi], 1
0x1800daeb1  jmp     short loc_1800DAEB7
0x1800daeb3  inc     eax
0x1800daeb5  jmp     short loc_1800DAE85
0x1800daeb7  mov     rcx, [rsp+48h+var_20]
0x1800daebc  test    rcx, rcx
0x1800daebf  jz      short loc_1800DAECD
0x1800daec1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800daec8  nop     dword ptr [rax+rax+00h]
0x1800daecd  mov     rcx, [rsp+48h+var_18]
0x1800daed2  test    rcx, rcx
0x1800daed5  jz      short loc_1800DAEE3
0x1800daed7  call    cs:__imp_BcdCloseObject
0x1800daede  nop     dword ptr [rax+rax+00h]
0x1800daee3  mov     eax, ebx
0x1800daee5  mov     rbx, [rsp+48h+arg_0]
0x1800daeea  mov     rsi, [rsp+48h+arg_8]
0x1800daeef  add     rsp, 40h
0x1800daef3  pop     rdi
0x1800daef4  retn
0x180128b6f  push    rbp
0x180128b71  sub     rsp, 20h
0x180128b75  mov     rbp, rdx
0x180128b78  mov     rcx, [rbp+28h]
0x180128b7c  test    rcx, rcx
0x180128b7f  jz      short loc_180128B8E
0x180128b81  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180128b88  nop     dword ptr [rax+rax+00h]
0x180128b8d  nop
0x180128b8e  mov     rcx, [rbp+30h]
0x180128b92  test    rcx, rcx
0x180128b95  jz      short loc_180128BA4
0x180128b97  call    cs:__imp_BcdCloseObject
0x180128b9e  nop     dword ptr [rax+rax+00h]
0x180128ba3  nop
0x180128ba4  add     rsp, 20h
0x180128ba8  pop     rbp
0x180128ba9  retn
```
