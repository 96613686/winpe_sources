# ProvSetProperty

- ea: `0x140002670`
- end: `0x14000277b`
- name: `ProvSetProperty`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140001170`
- `0x140002510`
- `0x140002670`
- `0x140002c48`
- `0x140003cf6`
- `0x14000a81c`
- `0x14000acd0`

## import_xrefs

- `cng!BCryptSetProperty` at `0x140002700`
- `cng!BCryptSetProperty` at `0x140002700`

## string_xrefs

- `0x1400026ab`: `CngChatConfiguration`

## pseudocode

```c
__int64 __fastcall ProvSetProperty(__int64 a1, const WCHAR *a2, UCHAR *a3, ULONG a4, ULONG dwFlags)
{
  __int64 v5; // rdi
  __int64 v9; // rax
  int v10; // edx
  NTSTATUS v11; // ebx
  int v12; // eax
  __int64 v13; // rcx

  v5 = 0;
  v9 = a1 ^ 0x4000000000000000LL;
  v10 = *(_DWORD *)(a1 ^ 0x4000000000000000LL);
  if ( v10 == 1816224072 )
    v5 = a1 ^ 0x4000000000000000LL;
  if ( v5 )
  {
    if ( !wcscmp_0(a2, L"CngChatConfiguration") )
    {
      v11 = ConfigSetChatConfig(a3);
      if ( v11 >= 0 )
      {
        ConfigApplyBounds();
        LogConfig("Set");
      }
    }
    else
    {
      v11 = BCryptSetProperty(*(BCRYPT_HANDLE *)(v5 + 16), a2, a3, a4, dwFlags);
      if ( v11 >= 0 )
      {
        if ( wcscmp_0(a2, L"ChainingMode")
          || (v12 = ConvertToInternalChainingMode((wchar_t *)a3), (*(_DWORD *)(v5 + 8) = v12) == 0) )
        {
          *(_BYTE *)(v5 + 12) = 1;
        }
      }
    }
  }
  else
  {
    v13 = 0;
    if ( v10 == 2034983240 )
      v13 = v9;
    if ( v13 )
      return (unsigned int)ProvSetKeyProperty(v13, a2, a3, a4, dwFlags);
    else
      return (unsigned int)-1073741816;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140002670  push    rbx
0x140002672  push    rbp
0x140002673  push    rsi
0x140002674  push    rdi
0x140002675  push    r14
0x140002677  sub     rsp, 30h
0x14000267b  xor     edi, edi
0x14000267d  mov     esi, r9d
0x140002680  mov     rax, rcx
0x140002683  mov     r14, rdx
0x140002686  mov     rcx, 4000000000000000h
0x140002690  mov     rbp, r8
0x140002693  xor     rax, rcx
0x140002696  mov     edx, [rax]
0x140002698  cmp     edx, 6C416148h
0x14000269e  cmovz   rdi, rax
0x1400026a2  test    rdi, rdi
0x1400026a5  jz      loc_14000273D
0x1400026ab  lea     rdx, aCngchatconfigu; "CngChatConfiguration"
0x1400026b2  mov     rcx, r14; Str1
0x1400026b5  call    wcscmp_0
0x1400026ba  test    eax, eax
0x1400026bc  jnz     short loc_1400026E8
0x1400026be  mov     edx, esi
0x1400026c0  mov     rcx, rbp
0x1400026c3  call    ConfigSetChatConfig
0x1400026c8  mov     ebx, eax
0x1400026ca  test    eax, eax
0x1400026cc  js      loc_14000276D
0x1400026d2  call    ConfigApplyBounds
0x1400026d7  lea     rcx, aSet; "Set"
0x1400026de  call    LogConfig
0x1400026e3  jmp     loc_14000276D
0x1400026e8  mov     eax, [rsp+58h+arg_20]
0x1400026ef  mov     r9d, esi; cbInput
0x1400026f2  mov     rcx, [rdi+10h]; hObject
0x1400026f6  mov     r8, rbp; pbInput
0x1400026f9  mov     rdx, r14; pszProperty
0x1400026fc  mov     [rsp+58h+dwFlags], eax; dwFlags
0x140002700  call    cs:__imp_BCryptSetProperty
0x140002707  nop     dword ptr [rax+rax+00h]
0x14000270c  mov     ebx, eax
0x14000270e  test    eax, eax
0x140002710  js      short loc_14000276D
0x140002712  lea     rdx, aChainingmode; "ChainingMode"
0x140002719  mov     rcx, r14; Str1
0x14000271c  call    wcscmp_0
0x140002721  test    eax, eax
0x140002723  jnz     short loc_140002737
0x140002725  mov     rdx, rsi
0x140002728  mov     rcx, rbp; Str1
0x14000272b  call    ConvertToInternalChainingMode
0x140002730  mov     [rdi+8], eax
0x140002733  test    eax, eax
0x140002735  jnz     short loc_14000276D
0x140002737  mov     byte ptr [rdi+0Ch], 1
0x14000273b  jmp     short loc_14000276D
0x14000273d  xor     ecx, ecx
0x14000273f  cmp     edx, 794B6148h
0x140002745  cmovz   rcx, rax
0x140002749  test    rcx, rcx
0x14000274c  jz      short loc_140002768
0x14000274e  mov     eax, [rsp+58h+arg_20]
0x140002755  mov     r9d, esi
0x140002758  mov     rdx, r14
0x14000275b  mov     [rsp+58h+dwFlags], eax
0x14000275f  call    ProvSetKeyProperty
0x140002764  mov     ebx, eax
0x140002766  jmp     short loc_14000276D
0x140002768  mov     ebx, 0C0000008h
0x14000276d  mov     eax, ebx
0x14000276f  add     rsp, 30h
0x140002773  pop     r14
0x140002775  pop     rdi
0x140002776  pop     rsi
0x140002777  pop     rbp
0x140002778  pop     rbx
0x140002779  retn
```
