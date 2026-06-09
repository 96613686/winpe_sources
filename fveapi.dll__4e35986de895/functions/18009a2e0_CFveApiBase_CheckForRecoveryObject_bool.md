# CFveApiBase::CheckForRecoveryObject(bool *)

- ea: `0x18009a2e0`
- end: `0x18009a477`
- name: `?CheckForRecoveryObject@CFveApiBase@@KAJPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(bool *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180044f70`

## callees

- `0x18000ba30`
- `0x180018b10`
- `0x18009a2e0`
- `0x18009befc`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18009a40c`
- `bcd!BcdCloseObject` at `0x18009a42f`
- `bcd!BcdCloseObject` at `0x1801246da`
- `bcd!BcdCloseObject` at `0x1801246ff`
- `bcd!BcdCloseObject` at `0x18009a40c`
- `bcd!BcdCloseObject` at `0x18009a42f`
- `bcd!BcdCloseObject` at `0x1801246da`
- `bcd!BcdCloseObject` at `0x1801246ff`
- `bcd!BcdOpenObject` at `0x18009a35d`
- `bcd!BcdOpenObject` at `0x18009a3db`
- `bcd!BcdOpenObject` at `0x18009a35d`
- `bcd!BcdOpenObject` at `0x18009a3db`
- `bcd!BcdCloseStore` at `0x18009a445`
- `bcd!BcdCloseStore` at `0x180124715`
- `bcd!BcdCloseStore` at `0x18009a445`
- `bcd!BcdCloseStore` at `0x180124715`
- `bcd!BcdOpenSystemStore` at `0x18009a32f`
- `bcd!BcdOpenSystemStore` at `0x18009a32f`

## pseudocode

```c
__int64 __fastcall CFveApiBase::CheckForRecoveryObject(bool *a1, __int64 a2)
{
  char *v3; // rdi
  int v4; // eax
  __int64 v5; // rdx
  int BcdElementData; // ebx
  int v7; // eax
  unsigned int v8; // r14d
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v12; // [rsp+20h] [rbp-58h] BYREF
  void *v13; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+38h] [rbp-40h] BYREF
  void *v16; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h] BYREF

  v16 = 0;
  v15 = 0;
  v17 = 0;
  v3 = 0;
  v13 = 0;
  v12 = 0;
  *a1 = 0;
  v4 = BcdOpenSystemStore(&v15, a2);
  BcdElementData = FromNtStatus(v4);
  if ( BcdElementData >= 0 )
  {
    v7 = BcdOpenObject(v15, &GUID_CURRENT_BOOT_ENTRY, &v16);
    BcdElementData = FromNtStatus(v7);
    if ( BcdElementData >= 0 )
    {
      BcdElementData = CFveApiBase::GetBcdElementData(v16, 0x14000008u, &v13, &v12);
      if ( BcdElementData < 0 )
      {
        BcdElementData = 0;
LABEL_5:
        v3 = (char *)v13;
        goto LABEL_13;
      }
      if ( (v12 & 0xF) != 0 )
      {
        BcdElementData = -2147024809;
        goto LABEL_5;
      }
      v8 = v12 >> 4;
      v9 = 0;
      v14 = 0;
      v3 = (char *)v13;
      while ( v9 < v8 )
      {
        v10 = BcdOpenObject(v15, &v3[16 * v9], &v17);
        BcdElementData = FromNtStatus(v10);
        if ( BcdElementData >= 0 )
        {
          *a1 = 1;
          break;
        }
        BcdElementData = 0;
        v14 = ++v9;
      }
    }
  }
LABEL_13:
  if ( v17 )
    BcdCloseObject(v17);
  if ( v3 )
    CFveApiBase::FastFree(v3);
  if ( v16 )
    BcdCloseObject(v16);
  if ( v15 )
    BcdCloseStore(v15, v5);
  return (unsigned int)BcdElementData;
}

```

## disassembly

```asm
0x18009a2e0  mov     r11, rsp
0x18009a2e3  mov     [r11+10h], rbx
0x18009a2e7  mov     [r11+18h], rsi
0x18009a2eb  push    rdi
0x18009a2ec  push    r14
0x18009a2ee  push    r15
0x18009a2f0  sub     rsp, 60h
0x18009a2f4  mov     rax, cs:__security_cookie
0x18009a2fb  xor     rax, rsp
0x18009a2fe  mov     [rsp+78h+var_28], rax
0x18009a303  mov     r15, rcx
0x18009a306  mov     qword ptr [r11-38h], 0
0x18009a30e  mov     qword ptr [r11-40h], 0
0x18009a316  mov     qword ptr [r11-30h], 0
0x18009a31e  xor     edi, edi
0x18009a320  mov     [r11-50h], rdi
0x18009a324  mov     [rsp+78h+var_58], edi
0x18009a328  mov     [rcx], dil
0x18009a32b  lea     rcx, [r11-40h]
0x18009a32f  call    cs:__imp_BcdOpenSystemStore
0x18009a336  nop     dword ptr [rax+rax+00h]
0x18009a33b  mov     ecx, eax; int
0x18009a33d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009a342  mov     ebx, eax
0x18009a344  test    eax, eax
0x18009a346  js      loc_18009A402
0x18009a34c  lea     r8, [rsp+78h+var_38]
0x18009a351  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18009a358  mov     rcx, [rsp+78h+var_40]
0x18009a35d  call    cs:__imp_BcdOpenObject
0x18009a364  nop     dword ptr [rax+rax+00h]
0x18009a369  mov     ecx, eax; int
0x18009a36b  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009a370  mov     ebx, eax
0x18009a372  test    eax, eax
0x18009a374  js      loc_18009A402
0x18009a37a  lea     r9, [rsp+78h+var_58]; unsigned int *
0x18009a37f  lea     r8, [rsp+78h+var_50]; void **
0x18009a384  mov     edx, 14000008h; unsigned int
0x18009a389  mov     rcx, [rsp+78h+var_38]; void *
0x18009a38e  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18009a393  mov     ebx, eax
0x18009a395  test    eax, eax
0x18009a397  jns     short loc_18009A3A2
0x18009a399  xor     ebx, ebx
0x18009a39b  mov     rdi, [rsp+78h+var_50]
0x18009a3a0  jmp     short loc_18009A402
0x18009a3a2  mov     r14d, [rsp+78h+var_58]
0x18009a3a7  test    r14b, 0Fh
0x18009a3ab  jz      short loc_18009A3B4
0x18009a3ad  mov     ebx, 80070057h
0x18009a3b2  jmp     short loc_18009A39B
0x18009a3b4  shr     r14d, 4
0x18009a3b8  xor     esi, esi
0x18009a3ba  mov     [rsp+78h+var_48], esi
0x18009a3be  mov     rdi, [rsp+78h+var_50]
0x18009a3c3  cmp     esi, r14d
0x18009a3c6  jnb     short loc_18009A402
0x18009a3c8  mov     edx, esi
0x18009a3ca  shl     rdx, 4
0x18009a3ce  add     rdx, rdi
0x18009a3d1  lea     r8, [rsp+78h+var_30]
0x18009a3d6  mov     rcx, [rsp+78h+var_40]
0x18009a3db  call    cs:__imp_BcdOpenObject
0x18009a3e2  nop     dword ptr [rax+rax+00h]
0x18009a3e7  mov     ecx, eax; int
0x18009a3e9  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009a3ee  mov     ebx, eax
0x18009a3f0  test    eax, eax
0x18009a3f2  jns     short loc_18009A3FE
0x18009a3f4  xor     ebx, ebx
0x18009a3f6  inc     esi
0x18009a3f8  mov     [rsp+78h+var_48], esi
0x18009a3fc  jmp     short loc_18009A3C3
0x18009a3fe  mov     byte ptr [r15], 1
0x18009a402  mov     rcx, [rsp+78h+var_30]
0x18009a407  test    rcx, rcx
0x18009a40a  jz      short loc_18009A418
0x18009a40c  call    cs:__imp_BcdCloseObject
0x18009a413  nop     dword ptr [rax+rax+00h]
0x18009a418  test    rdi, rdi
0x18009a41b  jz      short loc_18009A425
0x18009a41d  mov     rcx, rdi; lpMem
0x18009a420  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18009a425  mov     rcx, [rsp+78h+var_38]
0x18009a42a  test    rcx, rcx
0x18009a42d  jz      short loc_18009A43B
0x18009a42f  call    cs:__imp_BcdCloseObject
0x18009a436  nop     dword ptr [rax+rax+00h]
0x18009a43b  mov     rcx, [rsp+78h+var_40]
0x18009a440  test    rcx, rcx
0x18009a443  jz      short loc_18009A451
0x18009a445  call    cs:__imp_BcdCloseStore
0x18009a44c  nop     dword ptr [rax+rax+00h]
0x18009a451  mov     eax, ebx
0x18009a453  mov     rcx, [rsp+78h+var_28]
0x18009a458  xor     rcx, rsp; StackCookie
0x18009a45b  call    __security_check_cookie
0x18009a460  lea     r11, [rsp+78h+var_18]
0x18009a465  mov     rbx, [r11+28h]
0x18009a469  mov     rsi, [r11+30h]
0x18009a46d  mov     rsp, r11
0x18009a470  pop     r15
0x18009a472  pop     r14
0x18009a474  pop     rdi
0x18009a475  retn
0x1801246c8  push    rbp
0x1801246ca  sub     rsp, 20h
0x1801246ce  mov     rbp, rdx
0x1801246d1  mov     rcx, [rbp+48h]
0x1801246d5  test    rcx, rcx
0x1801246d8  jz      short loc_1801246E7
0x1801246da  call    cs:__imp_BcdCloseObject
0x1801246e1  nop     dword ptr [rax+rax+00h]
0x1801246e6  nop
0x1801246e7  mov     rcx, [rbp+28h]; lpMem
0x1801246eb  test    rcx, rcx
0x1801246ee  jz      short loc_1801246F6
0x1801246f0  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1801246f5  nop
0x1801246f6  mov     rcx, [rbp+40h]
0x1801246fa  test    rcx, rcx
0x1801246fd  jz      short loc_18012470C
0x1801246ff  call    cs:__imp_BcdCloseObject
0x180124706  nop     dword ptr [rax+rax+00h]
0x18012470b  nop
0x18012470c  mov     rcx, [rbp+38h]
0x180124710  test    rcx, rcx
0x180124713  jz      short loc_180124722
0x180124715  call    cs:__imp_BcdCloseStore
0x18012471c  nop     dword ptr [rax+rax+00h]
0x180124721  nop
0x180124722  add     rsp, 20h
0x180124726  pop     rbp
0x180124727  retn
```
