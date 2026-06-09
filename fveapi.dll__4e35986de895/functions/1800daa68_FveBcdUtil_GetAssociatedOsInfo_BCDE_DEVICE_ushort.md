# FveBcdUtil::GetAssociatedOsInfo(_BCDE_DEVICE * *,ushort * *)

- ea: `0x1800daa68`
- end: `0x1800dabb0`
- name: `?GetAssociatedOsInfo@FveBcdUtil@@SAJPEAPEAU_BCDE_DEVICE@@PEAPEAG@Z`
- size: `328`
- prototype: `__int64 __fastcall(struct _BCDE_DEVICE **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800d6dcc`

## callees

- `0x180018b10`
- `0x1800da860`
- `0x1800daa68`
- `0x1800dabb8`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800dab52`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128ae1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128af7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dab52`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128ae1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128af7`
- `bcd!BcdCloseObject` at `0x1800dab75`
- `bcd!BcdCloseObject` at `0x180128b19`
- `bcd!BcdCloseObject` at `0x1800dab75`
- `bcd!BcdCloseObject` at `0x180128b19`
- `bcd!BcdOpenObject` at `0x1800daaf7`
- `bcd!BcdOpenObject` at `0x1800daaf7`
- `bcd!BcdCloseStore` at `0x1800dab86`
- `bcd!BcdCloseStore` at `0x180128b29`
- `bcd!BcdCloseStore` at `0x1800dab86`
- `bcd!BcdCloseStore` at `0x180128b29`
- `bcd!BcdOpenSystemStore` at `0x1800daab2`
- `bcd!BcdOpenSystemStore` at `0x1800daab2`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetAssociatedOsInfo(struct _BCDE_DEVICE **a1, unsigned __int16 **a2)
{
  int v3; // eax
  __int64 v4; // rdx
  int AssociatedOs; // ebx
  int v6; // eax
  void *v7; // rcx
  void *v9; // [rsp+28h] [rbp-50h] BYREF
  void *v10; // [rsp+30h] [rbp-48h] BYREF
  void *v11; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v12; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+48h] [rbp-30h]
  struct _GUID v14; // [rsp+50h] [rbp-28h] BYREF

  v14 = 0;
  v9 = 0;
  v11 = 0;
  v10 = 0;
  v13 = 0;
  v3 = BcdOpenSystemStore(&v9, a2);
  AssociatedOs = FromNtStatus(v3);
  if ( AssociatedOs >= 0 )
  {
    AssociatedOs = FveBcdUtil::GetAssociatedOs(v9, &v14);
    if ( AssociatedOs >= 0 )
    {
      v6 = BcdOpenObject(v9, &v14, &v11);
      AssociatedOs = FromNtStatus(v6);
      if ( AssociatedOs >= 0 )
      {
        AssociatedOs = FveBcdUtil::GetBcdElementData(v11, 0x11000001u, &v10, &v12);
        if ( AssociatedOs >= 0 )
        {
          *a1 = (struct _BCDE_DEVICE *)v10;
          v10 = 0;
        }
      }
    }
  }
  if ( v10 )
    operator delete(v10);
  v7 = v9;
  if ( v9 )
  {
    if ( v11 )
    {
      BcdCloseObject(v11);
      v7 = v9;
    }
    BcdCloseStore(v7, v4);
  }
  return (unsigned int)AssociatedOs;
}

```

## disassembly

```asm
0x1800daa68  mov     r11, rsp
0x1800daa6b  mov     [r11+10h], rbx
0x1800daa6f  push    rdi
0x1800daa70  sub     rsp, 70h
0x1800daa74  mov     rax, cs:__security_cookie
0x1800daa7b  xor     rax, rsp
0x1800daa7e  mov     [rsp+78h+var_18], rax
0x1800daa83  mov     rdi, rcx
0x1800daa86  xorps   xmm0, xmm0
0x1800daa89  movups  xmmword ptr [rsp+78h+var_28.Data1], xmm0
0x1800daa8e  mov     qword ptr [r11-50h], 0
0x1800daa96  mov     qword ptr [r11-40h], 0
0x1800daa9e  mov     qword ptr [r11-48h], 0
0x1800daaa6  mov     qword ptr [r11-30h], 0
0x1800daaae  lea     rcx, [r11-50h]
0x1800daab2  call    cs:__imp_BcdOpenSystemStore
0x1800daab9  nop     dword ptr [rax+rax+00h]
0x1800daabe  mov     ecx, eax; int
0x1800daac0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800daac5  mov     ebx, eax
0x1800daac7  mov     [rsp+78h+var_58], eax
0x1800daacb  test    eax, eax
0x1800daacd  js      short loc_1800DAB48
0x1800daacf  lea     rdx, [rsp+78h+var_28]; struct _GUID *
0x1800daad4  mov     rcx, [rsp+78h+var_50]; void *
0x1800daad9  call    ?GetAssociatedOs@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z; FveBcdUtil::GetAssociatedOs(void *,_GUID *)
0x1800daade  mov     ebx, eax
0x1800daae0  mov     [rsp+78h+var_58], eax
0x1800daae4  test    eax, eax
0x1800daae6  js      short loc_1800DAB48
0x1800daae8  lea     r8, [rsp+78h+var_40]
0x1800daaed  lea     rdx, [rsp+78h+var_28]
0x1800daaf2  mov     rcx, [rsp+78h+var_50]
0x1800daaf7  call    cs:__imp_BcdOpenObject
0x1800daafe  nop     dword ptr [rax+rax+00h]
0x1800dab03  mov     ecx, eax; int
0x1800dab05  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800dab0a  mov     ebx, eax
0x1800dab0c  mov     [rsp+78h+var_58], eax
0x1800dab10  test    eax, eax
0x1800dab12  js      short loc_1800DAB48
0x1800dab14  lea     r9, [rsp+78h+var_38]; unsigned int *
0x1800dab19  lea     r8, [rsp+78h+var_48]; void **
0x1800dab1e  mov     edx, 11000001h; unsigned int
0x1800dab23  mov     rcx, [rsp+78h+var_40]; void *
0x1800dab28  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800dab2d  mov     ebx, eax
0x1800dab2f  mov     [rsp+78h+var_58], eax
0x1800dab33  test    eax, eax
0x1800dab35  js      short loc_1800DAB48
0x1800dab37  mov     rax, [rsp+78h+var_48]
0x1800dab3c  mov     [rdi], rax
0x1800dab3f  mov     [rsp+78h+var_48], 0
0x1800dab48  mov     rcx, [rsp+78h+var_48]
0x1800dab4d  test    rcx, rcx
0x1800dab50  jz      short loc_1800DAB5E
0x1800dab52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800dab59  nop     dword ptr [rax+rax+00h]
0x1800dab5e  mov     rcx, [rsp+78h+var_50]
0x1800dab63  test    rcx, rcx
0x1800dab66  jz      short loc_1800DAB92
0x1800dab68  mov     rax, [rsp+78h+var_40]
0x1800dab6d  test    rax, rax
0x1800dab70  jz      short loc_1800DAB86
0x1800dab72  mov     rcx, rax
0x1800dab75  call    cs:__imp_BcdCloseObject
0x1800dab7c  nop     dword ptr [rax+rax+00h]
0x1800dab81  mov     rcx, [rsp+78h+var_50]
0x1800dab86  call    cs:__imp_BcdCloseStore
0x1800dab8d  nop     dword ptr [rax+rax+00h]
0x1800dab92  mov     eax, ebx
0x1800dab94  mov     rcx, [rsp+78h+var_18]
0x1800dab99  xor     rcx, rsp; StackCookie
0x1800dab9c  call    __security_check_cookie
0x1800daba1  mov     rbx, [rsp+78h+arg_8]
0x1800daba9  add     rsp, 70h
0x1800dabad  pop     rdi
0x1800dabae  retn
0x180128acf  push    rbp
0x180128ad1  sub     rsp, 20h
0x180128ad5  mov     rbp, rdx
0x180128ad8  mov     rcx, [rbp+30h]
0x180128adc  test    rcx, rcx
0x180128adf  jz      short loc_180128AEE
0x180128ae1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180128ae8  nop     dword ptr [rax+rax+00h]
0x180128aed  nop
0x180128aee  mov     rcx, [rbp+48h]
0x180128af2  test    rcx, rcx
0x180128af5  jz      short loc_180128B04
0x180128af7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180128afe  nop     dword ptr [rax+rax+00h]
0x180128b03  nop
0x180128b04  mov     rcx, [rbp+28h]
0x180128b08  test    rcx, rcx
0x180128b0b  jz      short loc_180128B36
0x180128b0d  mov     rax, [rbp+38h]
0x180128b11  test    rax, rax
0x180128b14  jz      short loc_180128B29
0x180128b16  mov     rcx, rax
0x180128b19  call    cs:__imp_BcdCloseObject
0x180128b20  nop     dword ptr [rax+rax+00h]
0x180128b25  mov     rcx, [rbp+28h]
0x180128b29  call    cs:__imp_BcdCloseStore
0x180128b30  nop     dword ptr [rax+rax+00h]
0x180128b35  nop
0x180128b36  add     rsp, 20h
0x180128b3a  pop     rbp
0x180128b3b  retn
```
