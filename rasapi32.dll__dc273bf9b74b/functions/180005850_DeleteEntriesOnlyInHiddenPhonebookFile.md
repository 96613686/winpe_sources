# DeleteEntriesOnlyInHiddenPhonebookFile

- ea: `0x180005850`
- end: `0x180005ae8`
- name: `DeleteEntriesOnlyInHiddenPhonebookFile`
- size: `664`
- prototype: `void __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000714c`

## callees

- `0x180005850`
- `0x180005af0`
- `0x180029390`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x1800c059c`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18000589c`
- `rtutils!TracePrintfExA` at `0x1800058d2`
- `rtutils!TracePrintfExA` at `0x1800059c6`
- `rtutils!TracePrintfExA` at `0x180005a29`
- `rtutils!TracePrintfExA` at `0x18000589c`
- `rtutils!TracePrintfExA` at `0x1800058d2`
- `rtutils!TracePrintfExA` at `0x1800059c6`
- `rtutils!TracePrintfExA` at `0x180005a29`

## string_xrefs

- `0x1800058c8`: `DeleteEntriesOnlyInHiddenPhonebookFile : WritePhonebookFile failed with %d`
- `0x180005890`: `DeleteEntriesOnlyInHiddenPhonebookFile ++`
- `0x180005a1d`: `DeleteEntriesOnlyInHiddenPhonebookFile : %S not found`
- `0x1800059bc`: `DeleteEntriesOnlyInHiddenPhonebookFile : %S found`

## pseudocode

```c
void __fastcall DeleteEntriesOnlyInHiddenPhonebookFile(__int64 *a1, __int64 a2)
{
  char *v4; // rcx
  __int64 *v5; // r14
  __int64 v6; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rcx

  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 878, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = (char *)WPP_GLOBAL_Control;
  }
  v5 = *(__int64 **)(a2 + 16);
  if ( v5 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "DeleteEntriesOnlyInHiddenPhonebookFile ++");
    v6 = *v5;
LABEL_6:
    while ( v6 )
    {
      v12 = *(_QWORD *)(v6 + 16);
      v6 = *(_QWORD *)(v6 + 8);
      if ( v12 )
      {
        if ( a1 )
          v13 = *a1;
        else
          v13 = 0;
        while ( v13 )
        {
          v14 = *(_QWORD *)(v13 + 16);
          v13 = *(_QWORD *)(v13 + 8);
          if ( v14 && !(unsigned int)CompareStringWrapW(*(PCNZWCH *)(v14 + 8), *(PCNZWCH *)(v12 + 8)) )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "DeleteEntriesOnlyInHiddenPhonebookFile : %S found",
                *(const wchar_t **)(v12 + 8));
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                879,
                &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                *(_QWORD *)(v12 + 8));
            }
            goto LABEL_6;
          }
        }
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "DeleteEntriesOnlyInHiddenPhonebookFile : %S not found",
            *(const wchar_t **)(v12 + 8));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            880,
            &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
            *(_QWORD *)(v12 + 8));
        }
        *(_DWORD *)(v12 + 540) = 1;
      }
    }
    v7 = WritePhonebookFile(a2, 0);
    v8 = v7;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "DeleteEntriesOnlyInHiddenPhonebookFile : WritePhonebookFile failed with %d",
        v7);
    if ( v8 )
    {
      v4 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_11:
        v9 = *v5;
        if ( *v5 )
        {
          do
          {
            v10 = v9;
            v9 = *(_QWORD *)(v9 + 8);
            v11 = *(_QWORD *)(v10 + 16);
            if ( v11 && *(_DWORD *)(v11 + 540) )
              DtlDeleteNodeWithDestroyFunc(v5, v10, DestroyEntryNode);
          }
          while ( v9 );
          v4 = (char *)WPP_GLOBAL_Control;
        }
        goto LABEL_12;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 881, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
    }
    v4 = (char *)WPP_GLOBAL_Control;
    goto LABEL_11;
  }
LABEL_12:
  if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 6u )
    WPP_SF_(*((_QWORD *)v4 + 2), 882, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
}

```

## disassembly

```asm
0x180005850  push    rbx
0x180005852  push    rbp
0x180005853  push    rsi
0x180005854  push    rdi
0x180005855  push    r13
0x180005857  push    r14
0x180005859  push    r15
0x18000585b  sub     rsp, 20h
0x18000585f  mov     rbp, rdx
0x180005862  mov     r15, rcx
0x180005865  mov     rcx, cs:WPP_GLOBAL_Control
0x18000586c  lea     r13, WPP_GLOBAL_Control
0x180005873  cmp     rcx, r13
0x180005876  jnz     loc_18000590D
0x18000587c  mov     r14, [rbp+10h]
0x180005880  test    r14, r14
0x180005883  jz      short loc_1800058EF
0x180005885  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000588b  cmp     ecx, 0FFFFFFFFh
0x18000588e  jz      short loc_1800058A2
0x180005890  lea     r8, aDeleteentrieso; "DeleteEntriesOnlyInHiddenPhonebookFile "...
0x180005897  mov     edx, 0Ch; dwFlags
0x18000589c  call    cs:__imp_TracePrintfExA
0x1800058a2  mov     rsi, [r14]
0x1800058a5  test    rsi, rsi
0x1800058a8  jnz     loc_18000596D
0x1800058ae  xor     edx, edx
0x1800058b0  mov     rcx, rbp
0x1800058b3  call    WritePhonebookFile
0x1800058b8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800058be  mov     ebx, eax
0x1800058c0  cmp     ecx, 0FFFFFFFFh
0x1800058c3  jz      short loc_1800058D8
0x1800058c5  mov     r9d, eax
0x1800058c8  lea     r8, aDeleteentrieso_1; "DeleteEntriesOnlyInHiddenPhonebookFile "...
0x1800058cf  lea     edx, [rsi+0Ch]; dwFlags
0x1800058d2  call    cs:__imp_TracePrintfExA
0x1800058d8  test    ebx, ebx
0x1800058da  jnz     loc_180005A6F
0x1800058e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058e7  mov     rbx, [r14]
0x1800058ea  test    rbx, rbx
0x1800058ed  jnz     short loc_180005942
0x1800058ef  cmp     rcx, r13
0x1800058f2  jz      short loc_1800058FE
0x1800058f4  test    byte ptr [rcx+1Ch], 80h
0x1800058f8  jnz     loc_180005AC4
0x1800058fe  add     rsp, 20h
0x180005902  pop     r15
0x180005904  pop     r14
0x180005906  pop     r13
0x180005908  pop     rdi
0x180005909  pop     rsi
0x18000590a  pop     rbp
0x18000590b  pop     rbx
0x18000590c  retn
0x18000590d  test    byte ptr [rcx+1Ch], 80h
0x180005911  jz      loc_18000587C
0x180005917  cmp     byte ptr [rcx+19h], 6
0x18000591b  jb      loc_18000587C
0x180005921  mov     rcx, [rcx+10h]
0x180005925  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000592c  mov     edx, 36Eh
0x180005931  call    WPP_SF_
0x180005936  mov     rcx, cs:WPP_GLOBAL_Control
0x18000593d  jmp     loc_18000587C
0x180005942  mov     rdx, rbx
0x180005945  mov     rbx, [rbx+8]
0x180005949  mov     rax, [rdx+10h]
0x18000594d  test    rax, rax
0x180005950  jz      short loc_18000595F
0x180005952  cmp     dword ptr [rax+21Ch], 0
0x180005959  jnz     loc_180005AB0
0x18000595f  test    rbx, rbx
0x180005962  jnz     short loc_180005942
0x180005964  mov     rcx, cs:WPP_GLOBAL_Control
0x18000596b  jmp     short loc_1800058EF
0x18000596d  mov     rdi, [rsi+10h]
0x180005971  mov     rsi, [rsi+8]
0x180005975  test    rdi, rdi
0x180005978  jz      loc_1800058A5
0x18000597e  test    r15, r15
0x180005981  jz      short loc_180005988
0x180005983  mov     rbx, [r15]
0x180005986  jmp     short loc_18000598A
0x180005988  xor     ebx, ebx
0x18000598a  test    rbx, rbx
0x18000598d  jz      short loc_180005A0E
0x18000598f  mov     rcx, [rbx+10h]
0x180005993  mov     rbx, [rbx+8]
0x180005997  test    rcx, rcx
0x18000599a  jz      short loc_18000598A
0x18000599c  mov     rdx, [rdi+8]; lpString2
0x1800059a0  mov     rcx, [rcx+8]; lpString1
0x1800059a4  call    CompareStringWrapW
0x1800059a9  test    eax, eax
0x1800059ab  jnz     short loc_18000598A
0x1800059ad  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800059b3  cmp     ecx, 0FFFFFFFFh
0x1800059b6  jz      short loc_1800059CC
0x1800059b8  mov     r9, [rdi+8]
0x1800059bc  lea     r8, aDeleteentrieso_2; "DeleteEntriesOnlyInHiddenPhonebookFile "...
0x1800059c3  lea     edx, [rax+0Ch]; dwFlags
0x1800059c6  call    cs:__imp_TracePrintfExA
0x1800059cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059d3  cmp     rcx, r13
0x1800059d6  jz      loc_1800058A5
0x1800059dc  test    byte ptr [rcx+1Ch], 80h
0x1800059e0  jz      loc_1800058A5
0x1800059e6  cmp     byte ptr [rcx+19h], 5
0x1800059ea  jb      loc_1800058A5
0x1800059f0  mov     r9, [rdi+8]
0x1800059f4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800059fb  mov     rcx, [rcx+10h]
0x1800059ff  mov     edx, 36Fh
0x180005a04  call    WPP_SF_S
0x180005a09  jmp     loc_1800058A5
0x180005a0e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005a14  cmp     ecx, 0FFFFFFFFh
0x180005a17  jz      short loc_180005A2F
0x180005a19  mov     r9, [rdi+8]
0x180005a1d  lea     r8, aDeleteentrieso_0; "DeleteEntriesOnlyInHiddenPhonebookFile "...
0x180005a24  mov     edx, 0Ch; dwFlags
0x180005a29  call    cs:__imp_TracePrintfExA
0x180005a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a36  cmp     rcx, r13
0x180005a39  jz      short loc_180005A60
0x180005a3b  test    byte ptr [rcx+1Ch], 80h
0x180005a3f  jz      short loc_180005A60
0x180005a41  cmp     byte ptr [rcx+19h], 5
0x180005a45  jb      short loc_180005A60
0x180005a47  mov     r9, [rdi+8]
0x180005a4b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180005a52  mov     rcx, [rcx+10h]
0x180005a56  mov     edx, 370h
0x180005a5b  call    WPP_SF_S
0x180005a60  mov     dword ptr [rdi+21Ch], 1
0x180005a6a  jmp     loc_1800058A5
0x180005a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a76  cmp     rcx, r13
0x180005a79  jz      loc_1800058E7
0x180005a7f  test    byte ptr [rcx+1Ch], 80h
0x180005a83  jz      loc_1800058E7
0x180005a89  cmp     byte ptr [rcx+19h], 2
0x180005a8d  jb      loc_1800058E7
0x180005a93  mov     rcx, [rcx+10h]
0x180005a97  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180005a9e  mov     edx, 371h
0x180005aa3  mov     r9d, ebx
0x180005aa6  call    WPP_SF_d
0x180005aab  jmp     loc_1800058E0
0x180005ab0  lea     r8, DestroyEntryNode
0x180005ab7  mov     rcx, r14
0x180005aba  call    DtlDeleteNodeWithDestroyFunc
0x180005abf  jmp     loc_18000595F
0x180005ac4  cmp     byte ptr [rcx+19h], 6
0x180005ac8  jb      loc_1800058FE
0x180005ace  mov     rcx, [rcx+10h]
0x180005ad2  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180005ad9  mov     edx, 372h
0x180005ade  call    WPP_SF_
0x180005ae3  jmp     loc_1800058FE
```
