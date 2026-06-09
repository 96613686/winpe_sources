# FveCounterClaim::GetAvailableDeviceLockCounters(ulong *)

- ea: `0x1800da544`
- end: `0x1800da7c7`
- name: `?GetAvailableDeviceLockCounters@FveCounterClaim@@CAJPEAK@Z`
- size: `643`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800da374`
- `0x1800da4b0`

## callees

- `0x180018b10`
- `0x1800da2d4`
- `0x1800da544`
- `0x1800dabb8`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800da760`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800da760`
- `bcd!BcdQueryObject` at `0x1800da5fb`
- `bcd!BcdQueryObject` at `0x1800da5fb`
- `bcd!BcdCloseObject` at `0x1800da61c`
- `bcd!BcdCloseObject` at `0x1800da6bd`
- `bcd!BcdCloseObject` at `0x1800da775`
- `bcd!BcdCloseObject` at `0x1800da78a`
- `bcd!BcdCloseObject` at `0x1800da61c`
- `bcd!BcdCloseObject` at `0x1800da6bd`
- `bcd!BcdCloseObject` at `0x1800da775`
- `bcd!BcdCloseObject` at `0x1800da78a`
- `bcd!BcdOpenObject` at `0x1800da5d1`
- `bcd!BcdOpenObject` at `0x1800da63f`
- `bcd!BcdOpenObject` at `0x1800da6f8`
- `bcd!BcdOpenObject` at `0x1800da5d1`
- `bcd!BcdOpenObject` at `0x1800da63f`
- `bcd!BcdOpenObject` at `0x1800da6f8`
- `bcd!BcdCloseStore` at `0x1800da79f`
- `bcd!BcdCloseStore` at `0x1800da79f`
- `bcd!BcdOpenSystemStore` at `0x1800da5a5`
- `bcd!BcdOpenSystemStore` at `0x1800da5a5`

## pseudocode

```c
__int64 __fastcall FveCounterClaim::GetAvailableDeviceLockCounters(unsigned int *a1, __int64 a2)
{
  int v3; // eax
  char *v4; // rdx
  int BcdElement; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int BcdElementData; // eax
  char *v10; // r14
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // edi
  unsigned int i; // esi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v19; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+28h] [rbp-50h] BYREF
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  void *v22; // [rsp+38h] [rbp-40h] BYREF
  void *v23; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+48h] [rbp-30h] BYREF
  __int128 v25; // [rsp+50h] [rbp-28h] BYREF

  *a1 = 65538;
  v21 = 0;
  v22 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v20 = 0;
  v19 = 0;
  v3 = BcdOpenSystemStore(&v21, a2);
  BcdElement = FromNtStatus(v3);
  if ( BcdElement >= 0 )
  {
    v6 = BcdOpenObject(v21, &GUID_CURRENT_BOOT_ENTRY, &v19);
    BcdElement = FromNtStatus(v6);
    if ( BcdElement >= 0 )
    {
      v7 = BcdQueryObject(v19, 0, 0, &v25);
      BcdElement = FromNtStatus(v7);
      if ( BcdElement >= 0 )
      {
        BcdCloseObject(v19);
        v19 = 0;
        v8 = BcdOpenObject(v21, &GUID_WINDOWS_BOOTMGR, &v22);
        BcdElement = FromNtStatus(v8);
        if ( BcdElement >= 0 )
        {
          BcdElementData = FveBcdUtil::GetBcdElementData(v22, 0x24000001u, &v23, &v20);
          v10 = (char *)v23;
          BcdElement = BcdElementData;
          if ( BcdElementData >= 0 )
          {
            if ( (v20 & 0xF) != 0 )
            {
              BcdElement = -2147024809;
            }
            else
            {
              v13 = v20 >> 4;
              for ( i = 0; i < v13; ++i )
              {
                if ( v19 )
                {
                  BcdCloseObject(v19);
                  v19 = 0;
                }
                v4 = &v10[16 * i];
                v15 = v25 - *(_QWORD *)v4;
                if ( (_QWORD)v25 == *(_QWORD *)v4 )
                  v15 = *((_QWORD *)&v25 + 1) - *((_QWORD *)v4 + 1);
                if ( v15 )
                {
                  v16 = BcdOpenObject(v21, v4, &v19);
                  BcdElement = FromNtStatus(v16);
                  if ( BcdElement < 0
                    || (BcdElement = FveBcdUtil::GetBcdElementData<unsigned __int64>(v19, v17, &v24), BcdElement < 0) )
                  {
                    if ( BcdElement != (unsigned int)FromNtStatus(-1073741275) )
                      break;
                    BcdElement = 0;
                  }
                  else if ( v24 == 65538 )
                  {
                    *a1 = 0;
                  }
                }
              }
            }
          }
          else
          {
            v11 = FromNtStatus(-1073741275);
            v12 = 0;
            if ( BcdElement != v11 )
              v12 = BcdElement;
            BcdElement = v12;
          }
          if ( v10 )
            operator delete(v10);
        }
      }
    }
  }
  if ( v22 )
    BcdCloseObject(v22);
  if ( v19 )
    BcdCloseObject(v19);
  if ( v21 )
    BcdCloseStore(v21, v4);
  return (unsigned int)BcdElement;
}

```

## disassembly

```asm
0x1800da544  push    rbp
0x1800da546  push    rbx
0x1800da547  push    rsi
0x1800da548  push    rdi
0x1800da549  push    r14
0x1800da54b  push    r15
0x1800da54d  mov     rbp, rsp
0x1800da550  sub     rsp, 78h
0x1800da554  mov     rax, cs:__security_cookie
0x1800da55b  xor     rax, rsp
0x1800da55e  mov     [rbp+var_18], rax
0x1800da562  mov     r15, rcx
0x1800da565  mov     dword ptr [rcx], 10002h
0x1800da56b  xorps   xmm0, xmm0
0x1800da56e  mov     [rbp+var_48], 0
0x1800da576  lea     rcx, [rbp+var_48]
0x1800da57a  mov     [rbp+var_40], 0
0x1800da582  movups  [rbp+var_28], xmm0
0x1800da586  mov     [rbp+var_30], 0
0x1800da58e  mov     [rbp+var_38], 0
0x1800da596  mov     [rbp+var_50], 0
0x1800da59d  mov     [rbp+var_58], 0
0x1800da5a5  call    cs:__imp_BcdOpenSystemStore
0x1800da5ac  nop     dword ptr [rax+rax+00h]
0x1800da5b1  mov     ecx, eax; int
0x1800da5b3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da5b8  mov     ebx, eax
0x1800da5ba  test    eax, eax
0x1800da5bc  js      loc_1800DA76C
0x1800da5c2  mov     rcx, [rbp+var_48]
0x1800da5c6  lea     r8, [rbp+var_58]
0x1800da5ca  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x1800da5d1  call    cs:__imp_BcdOpenObject
0x1800da5d8  nop     dword ptr [rax+rax+00h]
0x1800da5dd  mov     ecx, eax; int
0x1800da5df  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da5e4  mov     ebx, eax
0x1800da5e6  test    eax, eax
0x1800da5e8  js      loc_1800DA76C
0x1800da5ee  mov     rcx, [rbp+var_58]
0x1800da5f2  lea     r9, [rbp+var_28]
0x1800da5f6  xor     r8d, r8d
0x1800da5f9  xor     edx, edx
0x1800da5fb  call    cs:__imp_BcdQueryObject
0x1800da602  nop     dword ptr [rax+rax+00h]
0x1800da607  mov     ecx, eax; int
0x1800da609  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da60e  mov     ebx, eax
0x1800da610  test    eax, eax
0x1800da612  js      loc_1800DA76C
0x1800da618  mov     rcx, [rbp+var_58]
0x1800da61c  call    cs:__imp_BcdCloseObject
0x1800da623  nop     dword ptr [rax+rax+00h]
0x1800da628  mov     rcx, [rbp+var_48]
0x1800da62c  lea     r8, [rbp+var_40]
0x1800da630  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800da637  mov     [rbp+var_58], 0
0x1800da63f  call    cs:__imp_BcdOpenObject
0x1800da646  nop     dword ptr [rax+rax+00h]
0x1800da64b  mov     ecx, eax; int
0x1800da64d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da652  mov     ebx, eax
0x1800da654  test    eax, eax
0x1800da656  js      loc_1800DA76C
0x1800da65c  mov     rcx, [rbp+var_40]; void *
0x1800da660  lea     r9, [rbp+var_50]; unsigned int *
0x1800da664  lea     r8, [rbp+var_38]; void **
0x1800da668  mov     edx, 24000001h; unsigned int
0x1800da66d  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800da672  mov     r14, [rbp+var_38]
0x1800da676  mov     ebx, eax
0x1800da678  test    eax, eax
0x1800da67a  jns     short loc_1800DA694
0x1800da67c  mov     ecx, 0C0000225h; int
0x1800da681  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da686  xor     ecx, ecx
0x1800da688  cmp     ebx, eax
0x1800da68a  cmovnz  ecx, ebx
0x1800da68d  mov     ebx, ecx
0x1800da68f  jmp     loc_1800DA758
0x1800da694  mov     edi, [rbp+var_50]
0x1800da697  test    dil, 0Fh
0x1800da69b  jz      short loc_1800DA6A7
0x1800da69d  mov     ebx, 80070057h
0x1800da6a2  jmp     loc_1800DA758
0x1800da6a7  shr     edi, 4
0x1800da6aa  xor     esi, esi
0x1800da6ac  test    edi, edi
0x1800da6ae  jz      loc_1800DA758
0x1800da6b4  mov     rcx, [rbp+var_58]
0x1800da6b8  test    rcx, rcx
0x1800da6bb  jz      short loc_1800DA6D1
0x1800da6bd  call    cs:__imp_BcdCloseObject
0x1800da6c4  nop     dword ptr [rax+rax+00h]
0x1800da6c9  mov     [rbp+var_58], 0
0x1800da6d1  mov     rax, qword ptr [rbp+var_28]
0x1800da6d5  mov     edx, esi
0x1800da6d7  shl     rdx, 4
0x1800da6db  add     rdx, r14
0x1800da6de  sub     rax, [rdx]
0x1800da6e1  jnz     short loc_1800DA6EB
0x1800da6e3  mov     rax, qword ptr [rbp+var_28+8]
0x1800da6e7  sub     rax, [rdx+8]
0x1800da6eb  test    rax, rax
0x1800da6ee  jz      short loc_1800DA74E
0x1800da6f0  mov     rcx, [rbp+var_48]
0x1800da6f4  lea     r8, [rbp+var_58]
0x1800da6f8  call    cs:__imp_BcdOpenObject
0x1800da6ff  nop     dword ptr [rax+rax+00h]
0x1800da704  mov     ecx, eax; int
0x1800da706  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da70b  mov     ebx, eax
0x1800da70d  test    eax, eax
0x1800da70f  jns     short loc_1800DA723
0x1800da711  mov     ecx, 0C0000225h; int
0x1800da716  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da71b  cmp     ebx, eax
0x1800da71d  jnz     short loc_1800DA758
0x1800da71f  xor     ebx, ebx
0x1800da721  jmp     short loc_1800DA74E
0x1800da723  mov     rcx, [rbp+var_58]
0x1800da727  lea     r8, [rbp+var_30]
0x1800da72b  call    ??$GetBcdElementData@_K@FveBcdUtil@@SAJPEAXKPEA_K@Z; FveBcdUtil::GetBcdElementData<unsigned __int64>(void *,ulong,unsigned __int64 *)
0x1800da730  mov     ebx, eax
0x1800da732  test    eax, eax
0x1800da734  js      short loc_1800DA711
0x1800da736  mov     rcx, [rbp+var_30]
0x1800da73a  lea     rax, [rcx-10002h]
0x1800da741  test    rax, rax
0x1800da744  jnz     short loc_1800DA74E
0x1800da746  mov     [r15+rcx*4-40008h], eax
0x1800da74e  inc     esi
0x1800da750  cmp     esi, edi
0x1800da752  jb      loc_1800DA6B4
0x1800da758  test    r14, r14
0x1800da75b  jz      short loc_1800DA76C
0x1800da75d  mov     rcx, r14
0x1800da760  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800da767  nop     dword ptr [rax+rax+00h]
0x1800da76c  mov     rcx, [rbp+var_40]
0x1800da770  test    rcx, rcx
0x1800da773  jz      short loc_1800DA781
0x1800da775  call    cs:__imp_BcdCloseObject
0x1800da77c  nop     dword ptr [rax+rax+00h]
0x1800da781  mov     rcx, [rbp+var_58]
0x1800da785  test    rcx, rcx
0x1800da788  jz      short loc_1800DA796
0x1800da78a  call    cs:__imp_BcdCloseObject
0x1800da791  nop     dword ptr [rax+rax+00h]
0x1800da796  mov     rcx, [rbp+var_48]
0x1800da79a  test    rcx, rcx
0x1800da79d  jz      short loc_1800DA7AB
0x1800da79f  call    cs:__imp_BcdCloseStore
0x1800da7a6  nop     dword ptr [rax+rax+00h]
0x1800da7ab  mov     eax, ebx
0x1800da7ad  mov     rcx, [rbp+var_18]
0x1800da7b1  xor     rcx, rsp; StackCookie
0x1800da7b4  call    __security_check_cookie
0x1800da7b9  add     rsp, 78h
0x1800da7bd  pop     r15
0x1800da7bf  pop     r14
0x1800da7c1  pop     rdi
0x1800da7c2  pop     rsi
0x1800da7c3  pop     rbx
0x1800da7c4  pop     rbp
0x1800da7c5  retn
```
