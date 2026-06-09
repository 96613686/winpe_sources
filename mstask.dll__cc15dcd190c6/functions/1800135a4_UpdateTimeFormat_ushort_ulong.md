# UpdateTimeFormat(ushort *,ulong)

- ea: `0x1800135a4`
- end: `0x1800137b3`
- name: `?UpdateTimeFormat@@YAXPEAGK@Z`
- size: `527`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180015570`
- `0x180015b30`
- `0x180018a14`
- `0x18001923c`

## callees

- `0x180001840`
- `0x180006f90`
- `0x1800135a4`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800135ea`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180013629`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180013658`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180013692`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800135ea`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180013629`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180013658`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180013692`

## pseudocode

```c
void __fastcall UpdateTimeFormat(unsigned __int16 *a1)
{
  int v2; // esi
  BOOL v3; // edi
  int v4; // ebp
  int v5; // r14d
  __int64 v6; // rax
  int v7; // ecx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  const unsigned __int16 *v10; // r8
  WCHAR LCData[80]; // [rsp+20h] [rbp-D8h] BYREF

  if ( !GetLocaleInfoW(0x400u, 0x23u, LCData, 80) )
    goto LABEL_27;
  v2 = 1;
  if ( LCData[0] != 48 )
  {
    v3 = 0;
    v4 = 0;
    goto LABEL_6;
  }
  if ( !GetLocaleInfoW(0x400u, 0x1005u, LCData, 80) )
  {
LABEL_27:
    StringCchCopyW(a1, 0x1Eu, L"hh:mm tt");
    return;
  }
  v4 = 1;
  v3 = LCData[0] == 49;
LABEL_6:
  if ( !GetLocaleInfoW(0x400u, 0x25u, LCData, 80) )
    goto LABEL_27;
  if ( LCData[0] == 49 )
  {
    v5 = 5;
  }
  else
  {
    v2 = 0;
    v5 = 4;
  }
  if ( !GetLocaleInfoW(0x400u, 0x1Eu, LCData, 80) )
    goto LABEL_27;
  v6 = -1;
  do
    ++v6;
  while ( LCData[v6] );
  v7 = v6 + (v4 != 0 ? 3 : 0);
  v8 = 0;
  v9 = v5 + v7;
  if ( v9 <= 0x1E )
    v8 = v9;
  if ( !v8 )
    goto LABEL_27;
  *a1 = 0;
  if ( v4 )
  {
    if ( v3 )
      StringCchCopyW(a1, 0x1Eu, L"tt ");
    StringCchCatW(a1, 0x1Eu, L"h");
    if ( !v2 )
      goto LABEL_24;
    v10 = L"h";
  }
  else
  {
    StringCchCatW(a1, 0x1Eu, L"H");
    if ( !v2 )
      goto LABEL_24;
    v10 = L"H";
  }
  StringCchCatW(a1, 0x1Eu, v10);
LABEL_24:
  StringCchCatW(a1, 0x1Eu, LCData);
  StringCchCatW(a1, 0x1Eu, L"mm");
  if ( v4 )
  {
    if ( !v3 )
      StringCchCatW(a1, 0x1Eu, L" tt");
  }
}

```

## disassembly

```asm
0x1800135a4  mov     [rsp+arg_8], rbx
0x1800135a9  mov     [rsp+arg_10], rbp
0x1800135ae  push    rsi
0x1800135af  push    rdi
0x1800135b0  push    r12
0x1800135b2  push    r14
0x1800135b4  push    r15
0x1800135b6  sub     rsp, 0D0h
0x1800135bd  mov     rax, cs:__security_cookie
0x1800135c4  xor     rax, rsp
0x1800135c7  mov     [rsp+0F8h+var_38], rax
0x1800135cf  mov     r9d, 50h ; 'P'; cchData
0x1800135d5  lea     r8, [rsp+0F8h+LCData]; lpLCData
0x1800135da  mov     rbx, rcx
0x1800135dd  mov     r14d, 400h
0x1800135e3  mov     ecx, r14d; Locale
0x1800135e6  lea     edx, [r9-2Dh]; LCType
0x1800135ea  call    cs:__imp_GetLocaleInfoW
0x1800135f0  xor     r15d, r15d
0x1800135f3  mov     r12d, 1Eh
0x1800135f9  test    eax, eax
0x1800135fb  jz      loc_180013775
0x180013601  cmp     [rsp+0F8h+LCData], 30h ; '0'
0x180013607  lea     esi, [r12-1Dh]
0x18001360c  jz      short loc_180013616
0x18001360e  mov     edi, r15d
0x180013611  mov     ebp, r15d
0x180013614  jmp     short loc_180013646
0x180013616  mov     r9d, 50h ; 'P'; cchData
0x18001361c  lea     r8, [rsp+0F8h+LCData]; lpLCData
0x180013621  mov     edx, 1005h; LCType
0x180013626  mov     ecx, r14d; Locale
0x180013629  call    cs:__imp_GetLocaleInfoW
0x18001362f  test    eax, eax
0x180013631  jz      loc_180013775
0x180013637  cmp     [rsp+0F8h+LCData], 31h ; '1'
0x18001363d  mov     edi, r15d
0x180013640  mov     ebp, esi
0x180013642  setz    dil
0x180013646  mov     r9d, 50h ; 'P'; cchData
0x18001364c  lea     r8, [rsp+0F8h+LCData]; lpLCData
0x180013651  mov     ecx, r14d; Locale
0x180013654  lea     edx, [r9-2Bh]; LCType
0x180013658  call    cs:__imp_GetLocaleInfoW
0x18001365e  test    eax, eax
0x180013660  jz      loc_180013775
0x180013666  cmp     [rsp+0F8h+LCData], 31h ; '1'
0x18001366c  jnz     short loc_180013676
0x18001366e  mov     r14d, 5
0x180013674  jmp     short loc_18001367F
0x180013676  mov     esi, r15d
0x180013679  mov     r14d, 4
0x18001367f  mov     r9d, 50h ; 'P'; cchData
0x180013685  lea     r8, [rsp+0F8h+LCData]; lpLCData
0x18001368a  mov     edx, r12d; LCType
0x18001368d  mov     ecx, 400h; Locale
0x180013692  call    cs:__imp_GetLocaleInfoW
0x180013698  test    eax, eax
0x18001369a  jz      loc_180013775
0x1800136a0  mov     eax, ebp
0x1800136a2  lea     rdx, [rsp+0F8h+LCData]
0x1800136a7  neg     eax
0x1800136a9  sbb     ecx, ecx
0x1800136ab  and     ecx, 3
0x1800136ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800136b2  inc     rax
0x1800136b5  cmp     [rdx+rax*2], r15w
0x1800136ba  jnz     short loc_1800136B2
0x1800136bc  add     ecx, eax
0x1800136be  mov     eax, r15d
0x1800136c1  add     ecx, r14d
0x1800136c4  cmp     ecx, r12d
0x1800136c7  cmovbe  eax, ecx
0x1800136ca  test    eax, eax
0x1800136cc  jz      loc_180013775
0x1800136d2  mov     [rbx], r15w
0x1800136d6  test    ebp, ebp
0x1800136d8  jz      short loc_18001370F
0x1800136da  test    edi, edi
0x1800136dc  jz      short loc_1800136F0
0x1800136de  lea     r8, aTt; "tt "
0x1800136e5  mov     rdx, r12; unsigned __int64
0x1800136e8  mov     rcx, rbx; unsigned __int16 *
0x1800136eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800136f0  lea     r8, asc_18001E6F0; "h"
0x1800136f7  mov     rdx, r12; unsigned __int64
0x1800136fa  mov     rcx, rbx; unsigned __int16 *
0x1800136fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013702  test    esi, esi
0x180013704  jz      short loc_180013737
0x180013706  lea     r8, asc_18001E6F0; "h"
0x18001370d  jmp     short loc_18001372C
0x18001370f  lea     r8, asc_18001E6F4; "H"
0x180013716  mov     rdx, r12; unsigned __int64
0x180013719  mov     rcx, rbx; unsigned __int16 *
0x18001371c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013721  test    esi, esi
0x180013723  jz      short loc_180013737
0x180013725  lea     r8, asc_18001E6F4; "H"
0x18001372c  mov     rdx, r12; unsigned __int64
0x18001372f  mov     rcx, rbx; unsigned __int16 *
0x180013732  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013737  lea     r8, [rsp+0F8h+LCData]; unsigned __int16 *
0x18001373c  mov     rdx, r12; unsigned __int64
0x18001373f  mov     rcx, rbx; unsigned __int16 *
0x180013742  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013747  lea     r8, aMm; "mm"
0x18001374e  mov     rdx, r12; unsigned __int64
0x180013751  mov     rcx, rbx; unsigned __int16 *
0x180013754  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013759  test    ebp, ebp
0x18001375b  jz      short loc_180013787
0x18001375d  test    edi, edi
0x18001375f  jnz     short loc_180013787
0x180013761  lea     r8, aTt_0; " tt"
0x180013768  mov     rdx, r12; unsigned __int64
0x18001376b  mov     rcx, rbx; unsigned __int16 *
0x18001376e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013773  jmp     short loc_180013787
0x180013775  lea     r8, aHhMmTt; "hh:mm tt"
0x18001377c  mov     rdx, r12; unsigned __int64
0x18001377f  mov     rcx, rbx; unsigned __int16 *
0x180013782  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013787  mov     rcx, [rsp+0F8h+var_38]
0x18001378f  xor     rcx, rsp; StackCookie
0x180013792  call    __security_check_cookie
0x180013797  lea     r11, [rsp+0F8h+var_28]
0x18001379f  mov     rbx, [r11+38h]
0x1800137a3  mov     rbp, [r11+40h]
0x1800137a7  mov     rsp, r11
0x1800137aa  pop     r15
0x1800137ac  pop     r14
0x1800137ae  pop     r12
0x1800137b0  pop     rdi
0x1800137b1  pop     rsi
0x1800137b2  retn
```
