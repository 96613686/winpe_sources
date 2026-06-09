# CFveApiBase::GetAssociatedOs(void *,_GUID *)

- ea: `0x18009ba80`
- end: `0x18009bc78`
- name: `?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x1800566a4`
- `0x180073728`
- `0x180078adc`
- `0x18009c910`
- `0x18009dd3c`
- `0x1800bc56c`

## callees

- `0x1800090c0`
- `0x18000ba30`
- `0x180018b10`
- `0x180047570`
- `0x18009ba80`
- `0x18009befc`
- `0x18009c170`
- `0x18009d0b4`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18009bc33`
- `bcd!BcdCloseObject` at `0x1801247f4`
- `bcd!BcdCloseObject` at `0x18009bc33`
- `bcd!BcdCloseObject` at `0x1801247f4`
- `bcd!BcdOpenObject` at `0x18009bb32`
- `bcd!BcdOpenObject` at `0x18009bb32`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetAssociatedOs(void *a1, struct _GUID *a2)
{
  unsigned __int8 v4; // r14
  int DoesRegKeyExist; // ebx
  int v6; // eax
  int BcdElementData; // eax
  unsigned int v8; // esi
  unsigned int i; // edi
  struct _GUID *v10; // r12
  int IsAssociatedOS; // eax
  unsigned __int8 v13[4]; // [rsp+20h] [rbp-68h] BYREF
  int v14; // [rsp+24h] [rbp-64h]
  int v15; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v16; // [rsp+2Ch] [rbp-5Ch] BYREF
  void *lpMem; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-50h]
  void *v19; // [rsp+40h] [rbp-48h] BYREF
  struct _GUID v20; // [rsp+48h] [rbp-40h] BYREF

  v20 = 0;
  v19 = 0;
  lpMem = 0;
  v16 = 0;
  v4 = 0;
  v13[0] = 0;
  v15 = 0;
  DoesRegKeyExist = NgscbpDoesRegKeyExist(a1, a2, &v15);
  v14 = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    if ( !v15 )
    {
LABEL_3:
      DoesRegKeyExist = -2147024809;
      v14 = -2147024809;
      goto LABEL_18;
    }
    DoesRegKeyExist = CFveApiBase::GetCurrentOsGuid(a1, &v20);
    v14 = DoesRegKeyExist;
    if ( DoesRegKeyExist >= 0 )
    {
      v6 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v19);
      DoesRegKeyExist = FromNtStatus(v6);
      v14 = DoesRegKeyExist;
      if ( DoesRegKeyExist >= 0 )
      {
        BcdElementData = CFveApiBase::GetBcdElementData(v19, 0x24000001u, &lpMem, &v16);
        DoesRegKeyExist = FromNtStatus(BcdElementData);
        v14 = DoesRegKeyExist;
        if ( DoesRegKeyExist >= 0 )
        {
          if ( (v16 & 0xF) != 0 )
            goto LABEL_3;
          v8 = v16 >> 4;
          for ( i = 0; ; ++i )
          {
            v18 = i;
            if ( i >= v8 )
              break;
            v10 = (struct _GUID *)((char *)lpMem + 16 * i);
            IsAssociatedOS = CFveApiBase::IsAssociatedOS(a1, v10, &v20, v13);
            DoesRegKeyExist = FromNtStatus(IsAssociatedOS);
            v14 = DoesRegKeyExist;
            if ( DoesRegKeyExist < 0 )
              goto LABEL_18;
            v4 = v13[0];
            if ( v13[0] )
            {
              *a2 = *v10;
              break;
            }
          }
          if ( !v4 )
          {
            DoesRegKeyExist = -2147024894;
            v14 = -2147024894;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                &WPP_1559182127783aab3882fe828952d989_Traceguids,
                2147942402LL);
          }
        }
      }
    }
  }
LABEL_18:
  if ( v19 )
    BcdCloseObject(v19);
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  return (unsigned int)DoesRegKeyExist;
}

```

## disassembly

```asm
0x18009ba80  mov     r11, rsp
0x18009ba83  mov     [r11+18h], rbx
0x18009ba87  mov     [r11+20h], rsi
0x18009ba8b  push    rdi
0x18009ba8c  push    r12
0x18009ba8e  push    r13
0x18009ba90  push    r14
0x18009ba92  push    r15
0x18009ba94  sub     rsp, 60h
0x18009ba98  mov     rax, cs:__security_cookie
0x18009ba9f  xor     rax, rsp
0x18009baa2  mov     [rsp+88h+var_30], rax
0x18009baa7  mov     r13, rdx
0x18009baaa  mov     r15, rcx
0x18009baad  xorps   xmm0, xmm0
0x18009bab0  movups  xmmword ptr [rsp+88h+var_40.Data1], xmm0
0x18009bab5  mov     qword ptr [r11-48h], 0
0x18009babd  mov     qword ptr [r11-58h], 0
0x18009bac5  mov     [rsp+88h+var_5C], 0
0x18009bacd  xor     r14b, r14b
0x18009bad0  mov     [r11-68h], r14b
0x18009bad4  mov     [rsp+88h+var_60], 0
0x18009badc  lea     r8, [r11-60h]
0x18009bae0  call    NgscbpDoesRegKeyExist
0x18009bae5  mov     ebx, eax
0x18009bae7  mov     [rsp+88h+var_64], eax
0x18009baeb  test    eax, eax
0x18009baed  js      loc_18009BC29
0x18009baf3  cmp     [rsp+88h+var_60], 0
0x18009baf8  jnz     short loc_18009BB08
0x18009bafa  mov     ebx, 80070057h
0x18009baff  mov     [rsp+88h+var_64], ebx
0x18009bb03  jmp     loc_18009BC29
0x18009bb08  lea     rdx, [rsp+88h+var_40]; struct _GUID *
0x18009bb0d  mov     rcx, r15; void *
0x18009bb10  call    ?GetCurrentOsGuid@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetCurrentOsGuid(void *,_GUID *)
0x18009bb15  mov     ebx, eax
0x18009bb17  mov     [rsp+88h+var_64], eax
0x18009bb1b  test    eax, eax
0x18009bb1d  js      loc_18009BC29
0x18009bb23  lea     r8, [rsp+88h+var_48]
0x18009bb28  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18009bb2f  mov     rcx, r15
0x18009bb32  call    cs:__imp_BcdOpenObject
0x18009bb39  nop     dword ptr [rax+rax+00h]
0x18009bb3e  mov     ecx, eax; int
0x18009bb40  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009bb45  mov     ebx, eax
0x18009bb47  mov     [rsp+88h+var_64], eax
0x18009bb4b  test    eax, eax
0x18009bb4d  js      loc_18009BC29
0x18009bb53  lea     r9, [rsp+88h+var_5C]; unsigned int *
0x18009bb58  lea     r8, [rsp+88h+lpMem]; void **
0x18009bb5d  mov     edx, 24000001h; unsigned int
0x18009bb62  mov     rcx, [rsp+88h+var_48]; void *
0x18009bb67  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18009bb6c  mov     ecx, eax; int
0x18009bb6e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009bb73  mov     ebx, eax
0x18009bb75  mov     [rsp+88h+var_64], eax
0x18009bb79  test    eax, eax
0x18009bb7b  js      loc_18009BC29
0x18009bb81  mov     esi, [rsp+88h+var_5C]
0x18009bb85  test    sil, 0Fh
0x18009bb89  jnz     loc_18009BAFA
0x18009bb8f  shr     esi, 4
0x18009bb92  xor     edi, edi
0x18009bb94  mov     [rsp+88h+var_50], edi
0x18009bb98  cmp     edi, esi
0x18009bb9a  jnb     short loc_18009BBE9
0x18009bb9c  mov     r12d, edi
0x18009bb9f  shl     r12, 4
0x18009bba3  add     r12, [rsp+88h+lpMem]
0x18009bba8  lea     r9, [rsp+88h+var_68]; unsigned __int8 *
0x18009bbad  lea     r8, [rsp+88h+var_40]; struct _GUID *
0x18009bbb2  mov     rdx, r12; struct _GUID *
0x18009bbb5  mov     rcx, r15; void *
0x18009bbb8  call    ?IsAssociatedOS@CFveApiBase@@KAJPEAXPEAU_GUID@@1PEAE@Z; CFveApiBase::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)
0x18009bbbd  mov     ecx, eax; int
0x18009bbbf  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009bbc4  mov     ebx, eax
0x18009bbc6  mov     [rsp+88h+var_64], eax
0x18009bbca  test    eax, eax
0x18009bbcc  js      short loc_18009BC29
0x18009bbce  mov     r14b, [rsp+88h+var_68]
0x18009bbd3  test    r14b, r14b
0x18009bbd6  jz      short loc_18009BBE5
0x18009bbd8  movups  xmm0, xmmword ptr [r12]
0x18009bbdd  movdqu  xmmword ptr [r13+0], xmm0
0x18009bbe3  jmp     short loc_18009BBE9
0x18009bbe5  inc     edi
0x18009bbe7  jmp     short loc_18009BB94
0x18009bbe9  test    r14b, r14b
0x18009bbec  jnz     short loc_18009BC29
0x18009bbee  mov     ebx, 80070002h
0x18009bbf3  mov     [rsp+88h+var_64], ebx
0x18009bbf7  lea     rax, WPP_GLOBAL_Control
0x18009bbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc05  cmp     rcx, rax
0x18009bc08  jz      short loc_18009BC29
0x18009bc0a  test    byte ptr [rcx+1Ch], 2
0x18009bc0e  jz      short loc_18009BC29
0x18009bc10  mov     edx, 14h
0x18009bc15  mov     r9d, ebx
0x18009bc18  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009bc1f  mov     rcx, [rcx+10h]
0x18009bc23  call    WPP_SF_d
0x18009bc28  nop
0x18009bc29  mov     rcx, [rsp+88h+var_48]
0x18009bc2e  test    rcx, rcx
0x18009bc31  jz      short loc_18009BC3F
0x18009bc33  call    cs:__imp_BcdCloseObject
0x18009bc3a  nop     dword ptr [rax+rax+00h]
0x18009bc3f  mov     rcx, [rsp+88h+lpMem]; lpMem
0x18009bc44  test    rcx, rcx
0x18009bc47  jz      short loc_18009BC4E
0x18009bc49  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18009bc4e  mov     eax, ebx
0x18009bc50  mov     rcx, [rsp+88h+var_30]
0x18009bc55  xor     rcx, rsp; StackCookie
0x18009bc58  call    __security_check_cookie
0x18009bc5d  lea     r11, [rsp+88h+var_28]
0x18009bc62  mov     rbx, [r11+40h]
0x18009bc66  mov     rsi, [r11+48h]
0x18009bc6a  mov     rsp, r11
0x18009bc6d  pop     r15
0x18009bc6f  pop     r14
0x18009bc71  pop     r13
0x18009bc73  pop     r12
0x18009bc75  pop     rdi
0x18009bc76  retn
0x1801247e2  push    rbp
0x1801247e4  sub     rsp, 20h
0x1801247e8  mov     rbp, rdx
0x1801247eb  mov     rcx, [rbp+40h]
0x1801247ef  test    rcx, rcx
0x1801247f2  jz      short loc_180124801
0x1801247f4  call    cs:__imp_BcdCloseObject
0x1801247fb  nop     dword ptr [rax+rax+00h]
0x180124800  nop
0x180124801  mov     rcx, [rbp+30h]; lpMem
0x180124805  test    rcx, rcx
0x180124808  jz      short loc_180124810
0x18012480a  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18012480f  nop
0x180124810  add     rsp, 20h
0x180124814  pop     rbp
0x180124815  retn
```
