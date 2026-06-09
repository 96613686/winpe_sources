# I_SetupNCryptStorageProvider

- ea: `0x180006010`
- end: `0x1800061ba`
- name: `I_SetupNCryptStorageProvider`
- size: `426`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009c00`
- `0x18000a050`
- `0x180011190`
- `0x18001f548`

## callees

- `0x180004600`
- `0x180006010`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180006089`
- `ncrypt!NCryptOpenStorageProvider` at `0x180006089`
- `ncrypt!NCryptSetProperty` at `0x18000610b`
- `ncrypt!NCryptSetProperty` at `0x18000610b`

## string_xrefs

- `0x1800060fc`: `SmartCardReader`

## pseudocode

```c
__int64 __fastcall I_SetupNCryptStorageProvider(__int64 a1)
{
  STRSAFE_LPSTR v2; // rcx
  __int64 v3; // rcx
  SECURITY_STATUS v4; // esi
  BYTE *v5; // r8
  __int64 v6; // r9
  SECURITY_STATUS v8; // ebx

  WppTraceIndent(a1, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( !*(_QWORD *)(a1 + 136) )
  {
    v4 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)(a1 + 136), *(LPCWSTR *)(a1 + 88), 0);
    if ( v4 )
    {
      WppTraceIndent(v3, 2);
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          v4);
      }
    }
    else
    {
      v5 = *(BYTE **)a1;
      v6 = -1;
      while ( *(_WORD *)&v5[2 * v6++ + 2] != 0 )
        ;
      v8 = NCryptSetProperty(*(_QWORD *)(a1 + 136), L"SmartCardReader", v5, 2 * v6 + 2, 0x40u);
      if ( v8 )
      {
        WppTraceIndent(v2, 2);
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v8);
        }
      }
    }
  }
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180006010  sub     rsp, 38h
0x180006014  mov     [rsp+38h+arg_0], rbx
0x180006019  xor     edx, edx
0x18000601b  mov     [rsp+38h+arg_8], rbp
0x180006020  mov     rbx, rcx
0x180006023  mov     [rsp+38h+var_8], rdi
0x180006028  call    WppTraceIndent
0x18000602d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006034  lea     rbp, WPP_GLOBAL_Control
0x18000603b  cmp     rcx, rbp
0x18000603e  jz      short loc_180006068
0x180006040  test    byte ptr [rcx+1Ch], 2
0x180006044  jz      short loc_180006068
0x180006046  cmp     byte ptr [rcx+19h], 5
0x18000604a  jb      short loc_180006068
0x18000604c  mov     r9, cs:WPP_pszIndent
0x180006053  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000605a  mov     rcx, [rcx+10h]
0x18000605e  mov     edx, 10h
0x180006063  call    WPP_SF_s
0x180006068  cmp     qword ptr [rbx+88h], 0
0x180006070  jnz     loc_18000615E
0x180006076  mov     rdx, [rbx+58h]; pszProviderName
0x18000607a  lea     rcx, [rbx+88h]; phProvider
0x180006081  xor     r8d, r8d; dwFlags
0x180006084  mov     [rsp+38h+arg_10], rsi
0x180006089  call    cs:__imp_NCryptOpenStorageProvider
0x18000608f  mov     esi, eax
0x180006091  test    eax, eax
0x180006093  jz      short loc_1800060CE
0x180006095  mov     edx, 2
0x18000609a  call    WppTraceIndent
0x18000609f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060a6  cmp     rcx, rbp
0x1800060a9  jz      loc_180006159
0x1800060af  test    byte ptr [rcx+1Ch], 1
0x1800060b3  jz      loc_180006159
0x1800060b9  cmp     byte ptr [rcx+19h], 2
0x1800060bd  jb      loc_180006159
0x1800060c3  mov     edx, 11h
0x1800060c8  mov     [rsp+38h+dwFlags], esi
0x1800060cc  jmp     short loc_180006142
0x1800060ce  mov     r8, [rbx]; pbInput
0x1800060d1  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800060d8  nop     dword ptr [rax+rax+00000000h]
0x1800060e0  cmp     word ptr [r8+r9*2+2], 0
0x1800060e7  lea     r9, [r9+1]
0x1800060eb  jnz     short loc_1800060E0
0x1800060ed  mov     rcx, [rbx+88h]; hObject
0x1800060f4  lea     r9d, ds:2[r9*2]; cbInput
0x1800060fc  lea     rdx, pszProperty; "SmartCardReader"
0x180006103  mov     [rsp+38h+dwFlags], 40h ; '@'; dwFlags
0x18000610b  call    cs:__imp_NCryptSetProperty
0x180006111  mov     ebx, eax
0x180006113  test    eax, eax
0x180006115  jz      short loc_180006159
0x180006117  mov     edx, 2
0x18000611c  call    WppTraceIndent
0x180006121  mov     rcx, cs:WPP_GLOBAL_Control
0x180006128  cmp     rcx, rbp
0x18000612b  jz      short loc_180006159
0x18000612d  test    byte ptr [rcx+1Ch], 1
0x180006131  jz      short loc_180006159
0x180006133  cmp     byte ptr [rcx+19h], 2
0x180006137  jb      short loc_180006159
0x180006139  mov     edx, 12h
0x18000613e  mov     [rsp+38h+dwFlags], ebx
0x180006142  mov     r9, cs:WPP_pszIndent
0x180006149  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180006150  mov     rcx, [rcx+10h]
0x180006154  call    WPP_SF_sD
0x180006159  mov     rsi, [rsp+38h+arg_10]
0x18000615e  mov     edx, 1
0x180006163  call    WppTraceIndent
0x180006168  mov     rcx, cs:WPP_GLOBAL_Control
0x18000616f  mov     rdi, [rsp+38h+var_8]
0x180006174  cmp     rcx, rbp
0x180006177  mov     rbp, [rsp+38h+arg_8]
0x18000617c  mov     rbx, [rsp+38h+arg_0]
0x180006181  jz      short loc_1800061B3
0x180006183  test    byte ptr [rcx+1Ch], 2
0x180006187  jz      short loc_1800061B3
0x180006189  cmp     byte ptr [rcx+19h], 5
0x18000618d  jb      short loc_1800061B3
0x18000618f  mov     r9, cs:WPP_pszIndent
0x180006196  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000619d  mov     rcx, [rcx+10h]
0x1800061a1  mov     edx, 13h
0x1800061a6  mov     [rsp+38h+dwFlags], 0
0x1800061ae  call    WPP_SF_sD
0x1800061b3  xor     eax, eax
0x1800061b5  add     rsp, 38h
0x1800061b9  retn
```
