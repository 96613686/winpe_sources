# ReadPhonebookFileEx

- ea: `0x1800083dc`
- end: `0x1800087aa`
- name: `ReadPhonebookFileEx`
- size: `974`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180007710`
- `0x180007b98`

## callees

- `0x1800079c0`
- `0x1800083dc`
- `0x1800087b0`
- `0x18000975c`
- `0x18002092c`
- `0x18003e28c`
- `0x18004e580`
- `0x18007e650`
- `0x18007ed3c`
- `0x1800d8720`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180008441`
- `rtutils!TracePrintfExA` at `0x1800084ea`
- `rtutils!TracePrintfExA` at `0x1800085b0`
- `rtutils!TracePrintfExA` at `0x1800086a1`
- `rtutils!TracePrintfExA` at `0x180008441`
- `rtutils!TracePrintfExA` at `0x1800084ea`
- `rtutils!TracePrintfExA` at `0x1800085b0`
- `rtutils!TracePrintfExA` at `0x1800086a1`

## string_xrefs

- `0x180008433`: `ReadPhonebookFileEx: called for pbk %S, flags %d`
- `0x1800084dc`: `ReadPhonebookFile returns %d`
- `0x18000859e`: `RASSQM: In ReadPhonebookFile Number of myuse profiles set %d`
- `0x18000868f`: `RASSQM: In ReadPhonebookFile Number of alluser profiles set %d`

## pseudocode

```c
__int64 __fastcall ReadPhonebookFileEx(const wchar_t *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // ebx
  _QWORD *v9; // rcx
  _DWORD *v10; // r12
  __int64 v11; // rcx
  unsigned int RegistryProfile; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  char *v15; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rdx

  v5 = a4;
  if ( a1 && a3 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        742,
        (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        (_DWORD)a1,
        a3,
        a4);
      goto LABEL_34;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 743, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a4);
LABEL_34:
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "ReadPhonebookFileEx: called for pbk %S, flags %d", a1, v5);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x80) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_Sd(v9[2], 744, (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (_DWORD)a1, v5);
  v10 = (_DWORD *)(a5 + 8);
  *(_DWORD *)(a5 + 8) = 0;
  *(_QWORD *)(a5 + 16) = DtlCreateList(v9);
  *(_QWORD *)(a5 + 48) = DtlCreateList(v11);
  *(_DWORD *)(a5 + 32) = v5;
  *(_QWORD *)a5 = 0;
  RegistryProfile = CalculatePhonebookPath((__int64)a1, a2, v5, (int *)(a5 + 8), (LPCWCH *)a5);
  v13 = RegistryProfile;
  if ( RegistryProfile )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v19 = 745;
LABEL_58:
    WPP_SF_d(v14[2], v19, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, RegistryProfile);
LABEL_8:
    ClosePhonebookFile(a5);
    goto LABEL_9;
  }
  if ( (unsigned int)IsRegistryRead((LPCWCH *)a5) )
  {
    RegistryProfile = ReadRegistryProfile(a5);
    v13 = RegistryProfile;
    if ( RegistryProfile )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_8;
      }
      v19 = 746;
      goto LABEL_58;
    }
  }
  else
  {
    RegistryProfile = ReadLegacyProfiles(a5, a3, v17, 0);
    v13 = RegistryProfile;
    if ( RegistryProfile )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_8;
      }
      v19 = 747;
      goto LABEL_58;
    }
  }
  if ( !a3 )
    goto LABEL_22;
  if ( !*(_DWORD *)(*(_QWORD *)(a5 + 16) + 16LL) )
  {
    v13 = 623;
    goto LABEL_10;
  }
LABEL_9:
  if ( v13 )
  {
LABEL_10:
    v15 = (char *)WPP_GLOBAL_Control;
    goto LABEL_11;
  }
LABEL_22:
  if ( *v10 )
  {
    if ( *v10 != 1 )
      goto LABEL_10;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "RASSQM: In ReadPhonebookFile Number of myuse profiles set %d",
        *(_DWORD *)(*(_QWORD *)(a5 + 16) + 16LL));
    v15 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v18 = 749;
LABEL_30:
      WPP_SF_d(
        *((_QWORD *)v15 + 2),
        v18,
        &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        *(unsigned int *)(*(_QWORD *)(a5 + 16) + 16LL));
      goto LABEL_10;
    }
  }
  else
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "RASSQM: In ReadPhonebookFile Number of alluser profiles set %d",
        *(_DWORD *)(*(_QWORD *)(a5 + 16) + 16LL));
    v15 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v18 = 748;
      goto LABEL_30;
    }
  }
LABEL_11:
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "ReadPhonebookFile returns %d", v13);
    v15 = (char *)WPP_GLOBAL_Control;
  }
  if ( v15 != (char *)&WPP_GLOBAL_Control && v15[28] < 0 && (unsigned __int8)v15[25] >= 6u )
    WPP_SF_d(*((_QWORD *)v15 + 2), 750, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x1800083dc  push    rbx
0x1800083de  push    rbp
0x1800083df  push    rsi
0x1800083e0  push    rdi
0x1800083e1  push    r12
0x1800083e3  push    r14
0x1800083e5  push    r15
0x1800083e7  sub     rsp, 30h
0x1800083eb  lea     r12, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800083f2  mov     ebx, r9d
0x1800083f5  mov     rbp, r8
0x1800083f8  mov     r15, rdx
0x1800083fb  mov     r14, rcx
0x1800083fe  mov     dil, 80h
0x180008401  test    rcx, rcx
0x180008404  jnz     loc_18000862D
0x18000840a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008411  lea     rsi, WPP_GLOBAL_Control
0x180008418  cmp     rcx, rsi
0x18000841b  jnz     loc_1800085FC
0x180008421  mov     eax, cs:g_dwTraceId
0x180008427  cmp     eax, 0FFFFFFFFh
0x18000842a  jz      short loc_18000844E
0x18000842c  mov     r9, r14
0x18000842f  mov     dword ptr [rsp+68h+var_48], ebx
0x180008433  lea     r8, aReadphonebookf_0; "ReadPhonebookFileEx: called for pbk %S,"...
0x18000843a  mov     edx, 0Ch; dwFlags
0x18000843f  mov     ecx, eax; dwTraceID
0x180008441  call    cs:__imp_TracePrintfExA
0x180008447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000844e  cmp     rcx, rsi
0x180008451  jnz     loc_180008517
0x180008457  mov     rdi, qword ptr [rsp+68h+arg_20]
0x18000845f  lea     r12, [rdi+8]
0x180008463  mov     dword ptr [r12], 0
0x18000846b  call    DtlCreateList
0x180008470  mov     [rdi+10h], rax
0x180008474  call    DtlCreateList
0x180008479  mov     r9, r12
0x18000847c  mov     [rdi+30h], rax
0x180008480  mov     r8d, ebx
0x180008483  mov     [rdi+20h], ebx
0x180008486  mov     rdx, r15
0x180008489  mov     qword ptr [rdi], 0
0x180008490  mov     rcx, r14
0x180008493  mov     [rsp+68h+var_48], rdi
0x180008498  call    CalculatePhonebookPath
0x18000849d  mov     ebx, eax
0x18000849f  test    eax, eax
0x1800084a1  jz      loc_180008548
0x1800084a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ae  cmp     rcx, rsi
0x1800084b1  jnz     loc_1800086D5
0x1800084b7  mov     rcx, rdi
0x1800084ba  call    ClosePhonebookFile
0x1800084bf  test    ebx, ebx
0x1800084c1  jz      loc_180008579
0x1800084c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ce  mov     eax, cs:g_dwTraceId
0x1800084d4  cmp     eax, 0FFFFFFFFh
0x1800084d7  jz      short loc_1800084F7
0x1800084d9  mov     r9d, ebx
0x1800084dc  lea     r8, aReadphonebookf_1; "ReadPhonebookFile returns %d"
0x1800084e3  mov     edx, 0Ch; dwFlags
0x1800084e8  mov     ecx, eax; dwTraceID
0x1800084ea  call    cs:__imp_TracePrintfExA
0x1800084f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084f7  cmp     rcx, rsi
0x1800084fa  jz      short loc_180008506
0x1800084fc  test    byte ptr [rcx+1Ch], 80h
0x180008500  jnz     loc_180008783
0x180008506  mov     eax, ebx
0x180008508  add     rsp, 30h
0x18000850c  pop     r15
0x18000850e  pop     r14
0x180008510  pop     r12
0x180008512  pop     rdi
0x180008513  pop     rsi
0x180008514  pop     rbp
0x180008515  pop     rbx
0x180008516  retn
0x180008517  test    [rcx+1Ch], dil
0x18000851b  jz      loc_180008457
0x180008521  cmp     byte ptr [rcx+19h], 5
0x180008525  jb      loc_180008457
0x18000852b  mov     rcx, [rcx+10h]
0x18000852f  mov     edx, 2E8h
0x180008534  mov     r9, r14
0x180008537  mov     dword ptr [rsp+68h+var_48], ebx
0x18000853b  mov     r8, r12
0x18000853e  call    WPP_SF_Sd
0x180008543  jmp     loc_180008457
0x180008548  mov     rcx, rdi
0x18000854b  call    IsRegistryRead
0x180008550  mov     rdx, rbp
0x180008553  mov     rcx, rdi; int
0x180008556  test    eax, eax
0x180008558  jnz     loc_1800086F0
0x18000855e  xor     r9d, r9d
0x180008561  call    ReadLegacyProfiles
0x180008566  mov     ebx, eax
0x180008568  test    eax, eax
0x18000856a  jnz     loc_18000872A
0x180008570  test    rbp, rbp
0x180008573  jnz     loc_18000876B
0x180008579  cmp     dword ptr [r12], 0
0x18000857e  jz      loc_180008680
0x180008584  cmp     dword ptr [r12], 1
0x180008589  jnz     loc_1800084C7
0x18000858f  mov     eax, cs:g_dwTraceId
0x180008595  cmp     eax, 0FFFFFFFFh
0x180008598  jz      short loc_1800085B6
0x18000859a  mov     r9, [rdi+10h]
0x18000859e  lea     r8, aRassqmInReadph; "RASSQM: In ReadPhonebookFile Number of "...
0x1800085a5  mov     edx, 0Ch; dwFlags
0x1800085aa  mov     ecx, eax; dwTraceID
0x1800085ac  mov     r9d, [r9+10h]
0x1800085b0  call    cs:__imp_TracePrintfExA
0x1800085b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085bd  cmp     rcx, rsi
0x1800085c0  jz      loc_1800084CE
0x1800085c6  test    byte ptr [rcx+1Ch], 80h
0x1800085ca  jz      loc_1800084CE
0x1800085d0  cmp     byte ptr [rcx+19h], 5
0x1800085d4  jb      loc_1800084CE
0x1800085da  mov     edx, 2EDh
0x1800085df  mov     r9, [rdi+10h]
0x1800085e3  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800085ea  mov     rcx, [rcx+10h]
0x1800085ee  mov     r9d, [r9+10h]
0x1800085f2  call    WPP_SF_d
0x1800085f7  jmp     loc_1800084C7
0x1800085fc  test    [rcx+1Ch], dil
0x180008600  jz      loc_180008421
0x180008606  cmp     byte ptr [rcx+19h], 6
0x18000860a  jb      loc_180008421
0x180008610  mov     rcx, [rcx+10h]
0x180008614  mov     edx, 2E7h
0x180008619  mov     r8, r12
0x18000861c  call    WPP_SF_d
0x180008621  mov     rcx, cs:WPP_GLOBAL_Control
0x180008628  jmp     loc_180008421
0x18000862d  test    rbp, rbp
0x180008630  jz      loc_18000840A
0x180008636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000863d  lea     rsi, WPP_GLOBAL_Control
0x180008644  cmp     rcx, rsi
0x180008647  jz      loc_180008421
0x18000864d  test    [rcx+1Ch], dil
0x180008651  jz      loc_180008421
0x180008657  cmp     byte ptr [rcx+19h], 6
0x18000865b  jb      loc_180008421
0x180008661  mov     rcx, [rcx+10h]
0x180008665  mov     edx, 2E6h
0x18000866a  mov     [rsp+68h+var_40], ebx
0x18000866e  mov     r9, r14
0x180008671  mov     r8, r12
0x180008674  mov     [rsp+68h+var_48], rbp
0x180008679  call    WPP_SF_SSD
0x18000867e  jmp     short loc_180008621
0x180008680  mov     eax, cs:g_dwTraceId
0x180008686  cmp     eax, 0FFFFFFFFh
0x180008689  jz      short loc_1800086A7
0x18000868b  mov     r9, [rdi+10h]
0x18000868f  lea     r8, aRassqmInReadph_0; "RASSQM: In ReadPhonebookFile Number of "...
0x180008696  mov     edx, 0Ch; dwFlags
0x18000869b  mov     ecx, eax; dwTraceID
0x18000869d  mov     r9d, [r9+10h]
0x1800086a1  call    cs:__imp_TracePrintfExA
0x1800086a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ae  cmp     rcx, rsi
0x1800086b1  jz      loc_1800084CE
0x1800086b7  test    byte ptr [rcx+1Ch], 80h
0x1800086bb  jz      loc_1800084CE
0x1800086c1  cmp     byte ptr [rcx+19h], 5
0x1800086c5  jb      loc_1800084CE
0x1800086cb  mov     edx, 2ECh
0x1800086d0  jmp     loc_1800085DF
0x1800086d5  test    byte ptr [rcx+1Ch], 80h
0x1800086d9  jz      loc_1800084B7
0x1800086df  cmp     byte ptr [rcx+19h], 2
0x1800086e3  jb      loc_1800084B7
0x1800086e9  mov     edx, 2E9h
0x1800086ee  jmp     short loc_180008753
0x1800086f0  call    ReadRegistryProfile
0x1800086f5  mov     ebx, eax
0x1800086f7  test    eax, eax
0x1800086f9  jz      loc_180008570
0x1800086ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008706  cmp     rcx, rsi
0x180008709  jz      loc_1800084B7
0x18000870f  test    byte ptr [rcx+1Ch], 80h
0x180008713  jz      loc_1800084B7
0x180008719  cmp     byte ptr [rcx+19h], 2
0x18000871d  jb      loc_1800084B7
0x180008723  mov     edx, 2EAh
0x180008728  jmp     short loc_180008753
0x18000872a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008731  cmp     rcx, rsi
0x180008734  jz      loc_1800084B7
0x18000873a  test    byte ptr [rcx+1Ch], 80h
0x18000873e  jz      loc_1800084B7
0x180008744  cmp     byte ptr [rcx+19h], 2
0x180008748  jb      loc_1800084B7
0x18000874e  mov     edx, 2EBh
0x180008753  mov     rcx, [rcx+10h]
0x180008757  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000875e  mov     r9d, eax
0x180008761  call    WPP_SF_d
0x180008766  jmp     loc_1800084B7
0x18000876b  mov     rax, [rdi+10h]
0x18000876f  cmp     dword ptr [rax+10h], 0
0x180008773  jnz     loc_1800084BF
0x180008779  mov     ebx, 26Fh
0x18000877e  jmp     loc_1800084C7
0x180008783  cmp     byte ptr [rcx+19h], 6
0x180008787  jb      loc_180008506
0x18000878d  mov     rcx, [rcx+10h]
0x180008791  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180008798  mov     edx, 2EEh
0x18000879d  mov     r9d, ebx
0x1800087a0  call    WPP_SF_d
0x1800087a5  jmp     loc_180008506
```
