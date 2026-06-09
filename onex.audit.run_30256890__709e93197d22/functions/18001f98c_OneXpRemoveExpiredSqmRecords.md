# OneXpRemoveExpiredSqmRecords

- ea: `0x18001f98c`
- end: `0x18001fb4f`
- name: `OneXpRemoveExpiredSqmRecords`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f690`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x18001f98c`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f99f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f99f`
- `MobileNetworking!ReleaseWriteLock` at `0x18001fb0b`
- `MobileNetworking!ReleaseWriteLock` at `0x18001fb0b`
- `MobileNetworking!AcquireWriteLock` at `0x18001f9f3`
- `MobileNetworking!AcquireWriteLock` at `0x18001f9f3`
- `MobileNetworking!FreeMemory` at `0x18001fade`
- `MobileNetworking!FreeMemory` at `0x18001fade`

## string_xrefs

- `0x18001f9de`: `OneXpRemoveExpiredSqmRecords`
- `0x18001face`: `OneXpRemoveExpiredSqmRecords`
- `0x18001faf6`: `OneXpRemoveExpiredSqmRecords`

## pseudocode

```c
__int64 OneXpRemoveExpiredSqmRecords()
{
  DWORD TickCount; // ebx
  __int64 v1; // rdx
  __int64 v2; // r9
  __int64 *v3; // rdi
  __int64 *v4; // rcx
  __int64 **v5; // rax
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 0;
  TickCount = GetTickCount();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 83, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
  AcquireWriteLock(g_OneXInfo, qword_18003DE28, "OneXpRemoveExpiredSqmRecords", 717);
  v1 = qword_18003DE18;
  if ( (__int64 *)qword_18003DE18 != &qword_18003DE18 )
  {
    while ( 1 )
    {
      v8 = v1;
      v2 = *(unsigned int *)(v1 + 56);
      v3 = *(__int64 **)v1;
      if ( TickCount < (unsigned int)v2 )
        break;
      if ( TickCount - (unsigned int)v2 >= 0x5265C00 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 85, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v2);
          v1 = v8;
        }
        v4 = *(__int64 **)v1;
        if ( *(_QWORD *)(*(_QWORD *)v1 + 8LL) != v1 )
          goto LABEL_25;
        v5 = *(__int64 ***)(v1 + 8);
        if ( *v5 != (__int64 *)v1 )
          goto LABEL_25;
        v6 = 751;
LABEL_19:
        *v5 = v4;
        v4[1] = (__int64)v5;
        FreeMemory(&v8, "OneXpRemoveExpiredSqmRecords", v6);
      }
      v1 = (__int64)v3;
      if ( v3 == &qword_18003DE18 )
        goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 84, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v2);
      v1 = v8;
    }
    v4 = *(__int64 **)v1;
    if ( *(_QWORD *)(*(_QWORD *)v1 + 8LL) != v1 || (v5 = *(__int64 ***)(v1 + 8), *v5 != (__int64 *)v1) )
LABEL_25:
      __fastfail(3u);
    v6 = 734;
    goto LABEL_19;
  }
LABEL_21:
  result = ReleaseWriteLock(g_OneXInfo, qword_18003DE28, "OneXpRemoveExpiredSqmRecords", 755);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 86, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x18001f98c  push    rbx
0x18001f98e  push    rsi
0x18001f98f  push    rdi
0x18001f990  push    r12
0x18001f992  sub     rsp, 28h
0x18001f996  mov     [rsp+48h+arg_0], 0
0x18001f99f  call    cs:__imp_GetTickCount
0x18001f9a5  mov     ebx, eax
0x18001f9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9ae  lea     rsi, WPP_GLOBAL_Control
0x18001f9b5  cmp     rcx, rsi
0x18001f9b8  jz      short loc_18001F9D8
0x18001f9ba  test    dword ptr [rcx+44h], 800h
0x18001f9c1  jz      short loc_18001F9D8
0x18001f9c3  mov     rcx, [rcx+38h]
0x18001f9c7  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001f9ce  mov     edx, 53h ; 'S'
0x18001f9d3  call    WPP_SF_
0x18001f9d8  mov     r9d, 2CDh
0x18001f9de  lea     r8, aOnexpremoveexp; "OneXpRemoveExpiredSqmRecords"
0x18001f9e5  lea     rdx, qword_18003DE28
0x18001f9ec  lea     rcx, g_OneXInfo
0x18001f9f3  call    cs:__imp_AcquireWriteLock
0x18001f9f9  mov     rdx, cs:qword_18003DE18
0x18001fa00  lea     r12, qword_18003DE18
0x18001fa07  cmp     rdx, r12
0x18001fa0a  jz      loc_18001FAF0
0x18001fa10  mov     [rsp+48h+arg_0], rdx
0x18001fa15  mov     r9d, [rdx+38h]
0x18001fa19  mov     rdi, [rdx]
0x18001fa1c  cmp     ebx, r9d
0x18001fa1f  jb      short loc_18001FA7F
0x18001fa21  mov     eax, ebx
0x18001fa23  sub     eax, r9d
0x18001fa26  cmp     eax, 5265C00h
0x18001fa2b  jb      loc_18001FAE4
0x18001fa31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa38  cmp     rcx, rsi
0x18001fa3b  jz      short loc_18001FA5D
0x18001fa3d  test    byte ptr [rcx+44h], 4
0x18001fa41  jz      short loc_18001FA5D
0x18001fa43  mov     rcx, [rcx+38h]
0x18001fa47  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001fa4e  mov     edx, 55h ; 'U'
0x18001fa53  call    WPP_SF_d
0x18001fa58  mov     rdx, [rsp+48h+arg_0]
0x18001fa5d  mov     rcx, [rdx]
0x18001fa60  cmp     [rcx+8], rdx
0x18001fa64  jnz     loc_18001FB48
0x18001fa6a  mov     rax, [rdx+8]
0x18001fa6e  cmp     [rax], rdx
0x18001fa71  jnz     loc_18001FB48
0x18001fa77  mov     r8d, 2EFh
0x18001fa7d  jmp     short loc_18001FACB
0x18001fa7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa86  cmp     rcx, rsi
0x18001fa89  jz      short loc_18001FAAB
0x18001fa8b  test    byte ptr [rcx+44h], 4
0x18001fa8f  jz      short loc_18001FAAB
0x18001fa91  mov     rcx, [rcx+38h]
0x18001fa95  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001fa9c  mov     edx, 54h ; 'T'
0x18001faa1  call    WPP_SF_d
0x18001faa6  mov     rdx, [rsp+48h+arg_0]
0x18001faab  mov     rcx, [rdx]
0x18001faae  cmp     [rcx+8], rdx
0x18001fab2  jnz     loc_18001FB48
0x18001fab8  mov     rax, [rdx+8]
0x18001fabc  cmp     [rax], rdx
0x18001fabf  jnz     loc_18001FB48
0x18001fac5  mov     r8d, 2DEh
0x18001facb  mov     [rax], rcx
0x18001face  lea     rdx, aOnexpremoveexp; "OneXpRemoveExpiredSqmRecords"
0x18001fad5  mov     [rcx+8], rax
0x18001fad9  lea     rcx, [rsp+48h+arg_0]
0x18001fade  call    cs:__imp_FreeMemory
0x18001fae4  mov     rdx, rdi
0x18001fae7  cmp     rdi, r12
0x18001faea  jnz     loc_18001FA10
0x18001faf0  mov     r9d, 2F3h
0x18001faf6  lea     r8, aOnexpremoveexp; "OneXpRemoveExpiredSqmRecords"
0x18001fafd  lea     rdx, qword_18003DE28
0x18001fb04  lea     rcx, g_OneXInfo
0x18001fb0b  call    cs:__imp_ReleaseWriteLock
0x18001fb11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb18  cmp     rcx, rsi
0x18001fb1b  jz      short loc_18001FB3E
0x18001fb1d  test    dword ptr [rcx+44h], 800h
0x18001fb24  jz      short loc_18001FB3E
0x18001fb26  mov     rcx, [rcx+38h]
0x18001fb2a  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001fb31  mov     edx, 56h ; 'V'
0x18001fb36  xor     r9d, r9d
0x18001fb39  call    WPP_SF_D
0x18001fb3e  add     rsp, 28h
0x18001fb42  pop     r12
0x18001fb44  pop     rdi
0x18001fb45  pop     rsi
0x18001fb46  pop     rbx
0x18001fb47  retn
0x18001fb48  mov     ecx, 3
0x18001fb4d  int     29h; Win8: RtlFailFast(ecx)
```
