# ReadLegacyProfiles

- ea: `0x18002092c`
- end: `0x180020ab7`
- name: `ReadLegacyProfiles`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800083dc`

## callees

- `0x18000714c`
- `0x18000b0f4`
- `0x18000b960`
- `0x18002092c`
- `0x180020ac0`
- `0x180020b18`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x1800209bb`
- `rtutils!TracePrintfExA` at `0x180020a7c`
- `rtutils!TracePrintfExA` at `0x1800209bb`
- `rtutils!TracePrintfExA` at `0x180020a7c`

## string_xrefs

- `0x1800209ac`: `ReadLegacyProfiles: ReadRasFile failed with %d`
- `0x180020aab`: `ReadLegacyProfiles: Syncmasterpbk failed with %d`
- `0x180020a94`: `ReadLegacyProfiles: ReadRasFile for hidden pbk failed with %d`
- `0x180020a70`: `ReadLegacyProfiles: GetLUAPhonebookPath: Failed %d`

## pseudocode

```c
__int64 __fastcall ReadLegacyProfiles(__int64 a1, int a2, int a3, __int64 a4)
{
  const WCHAR *v4; // rdi
  bool v5; // zf
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int LUAPhonebookPath; // eax
  __int16 v12; // r14
  int v13; // r14d
  unsigned int RasFile; // eax
  unsigned int v15; // eax
  const WCHAR *v17; // [rsp+60h] [rbp+8h] BYREF
  int v18; // [rsp+70h] [rbp+18h] BYREF

  v18 = a3;
  v4 = 0;
  v5 = (*(_DWORD *)(a1 + 32) & 0x800) == 0;
  v17 = 0;
  v18 = -1;
  if ( v5 )
  {
    if ( !(unsigned int)IsVirtualizationNeeded(a1) )
      goto LABEL_3;
    LUAPhonebookPath = GetLUAPhonebookPath(*(LPCWSTR *)a1, (__int64 *)&v17);
    v10 = LUAPhonebookPath;
    if ( LUAPhonebookPath )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ReadLegacyProfiles: GetLUAPhonebookPath: Failed %d", LUAPhonebookPath);
      v4 = v17;
      goto LABEL_11;
    }
    v4 = v17;
    if ( v17 )
    {
      v12 = *(_DWORD *)(a1 + 32);
      *(_DWORD *)(a1 + 32) |= 0x100u;
      v13 = v12 & 0x400;
      RasFile = ReadRasFile(v4, a4, (__int64)&v18);
      v10 = RasFile;
      if ( RasFile )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "ReadLegacyProfiles: ReadRasFile for hidden pbk failed with %d", RasFile);
      }
      else
      {
        v15 = SyncMasterPhonebookFile(*(_QWORD *)a1, a1, v13, a2, v18);
        v10 = v15;
        if ( v15 && g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "ReadLegacyProfiles: Syncmasterpbk failed with %d", v15);
      }
    }
    else
    {
LABEL_3:
      v9 = ReadRasFile(*(LPCWSTR *)a1, a4, 0);
      v10 = v9;
      if ( v9 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "ReadLegacyProfiles: ReadRasFile failed with %d", v9);
      }
    }
LABEL_11:
    Free0(v4);
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x18002092c  mov     rax, rsp
0x18002092f  mov     [rax+10h], rbx
0x180020933  mov     [rax+20h], rbp
0x180020937  mov     [rax+18h], r8d
0x18002093b  push    rsi
0x18002093c  push    rdi
0x18002093d  push    r12
0x18002093f  push    r14
0x180020941  push    r15
0x180020943  sub     rsp, 30h
0x180020947  xor     edi, edi
0x180020949  or      r12d, 0FFFFFFFFh
0x18002094d  test    dword ptr [rcx+20h], 800h
0x180020954  mov     r15, r9
0x180020957  mov     rbp, rdx
0x18002095a  mov     [rax+8], rdi
0x18002095e  mov     rsi, rcx
0x180020961  mov     [rax+18h], r12d
0x180020965  jnz     loc_180020A5E
0x18002096b  call    IsVirtualizationNeeded
0x180020970  test    eax, eax
0x180020972  jnz     short loc_1800209C3
0x180020974  mov     rcx, [rsi]
0x180020977  mov     r9, rsi
0x18002097a  mov     [rsp+58h+var_30], 0
0x180020983  xor     r8d, r8d
0x180020986  mov     rdx, rbp
0x180020989  mov     [rsp+58h+var_38], r15
0x18002098e  call    ReadRasFile
0x180020993  mov     ebx, eax
0x180020995  test    eax, eax
0x180020997  jz      loc_180020A3D
0x18002099d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800209a3  cmp     ecx, r12d
0x1800209a6  jz      loc_180020A3D
0x1800209ac  lea     r8, aReadlegacyprof_1; "ReadLegacyProfiles: ReadRasFile failed "...
0x1800209b3  mov     r9d, eax
0x1800209b6  mov     edx, 0Ch; dwFlags
0x1800209bb  call    cs:__imp_TracePrintfExA
0x1800209c1  jmp     short loc_180020A3D
0x1800209c3  mov     rcx, [rsi]; lpFileName
0x1800209c6  lea     rdx, [rsp+58h+arg_0]
0x1800209cb  call    GetLUAPhonebookPath
0x1800209d0  mov     ebx, eax
0x1800209d2  test    eax, eax
0x1800209d4  jnz     loc_180020A62
0x1800209da  mov     rdi, [rsp+58h+arg_0]
0x1800209df  test    rdi, rdi
0x1800209e2  jz      short loc_180020974
0x1800209e4  mov     eax, [rsi+20h]
0x1800209e7  mov     r9, rsi
0x1800209ea  mov     r14d, eax
0x1800209ed  xor     r8d, r8d
0x1800209f0  bts     eax, 8
0x1800209f4  mov     rdx, rbp
0x1800209f7  mov     [rsi+20h], eax
0x1800209fa  mov     rcx, rdi
0x1800209fd  lea     rax, [rsp+58h+arg_10]
0x180020a02  and     r14d, 400h
0x180020a09  mov     [rsp+58h+var_30], rax
0x180020a0e  mov     [rsp+58h+var_38], r15
0x180020a13  call    ReadRasFile
0x180020a18  mov     ebx, eax
0x180020a1a  test    eax, eax
0x180020a1c  jnz     short loc_180020A89
0x180020a1e  mov     eax, [rsp+58h+arg_10]
0x180020a22  mov     r9, rbp
0x180020a25  mov     rcx, [rsi]
0x180020a28  mov     r8d, r14d
0x180020a2b  mov     rdx, rsi
0x180020a2e  mov     dword ptr [rsp+58h+var_38], eax
0x180020a32  call    SyncMasterPhonebookFile
0x180020a37  mov     ebx, eax
0x180020a39  test    eax, eax
0x180020a3b  jnz     short loc_180020AA0
0x180020a3d  mov     rcx, rdi
0x180020a40  call    Free0
0x180020a45  mov     eax, ebx
0x180020a47  mov     rbx, [rsp+58h+arg_8]
0x180020a4c  mov     rbp, [rsp+58h+arg_18]
0x180020a51  add     rsp, 30h
0x180020a55  pop     r15
0x180020a57  pop     r14
0x180020a59  pop     r12
0x180020a5b  pop     rdi
0x180020a5c  pop     rsi
0x180020a5d  retn
0x180020a5e  xor     eax, eax
0x180020a60  jmp     short loc_180020A47
0x180020a62  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180020a68  cmp     ecx, r12d
0x180020a6b  jz      short loc_180020A82
0x180020a6d  mov     r9d, eax
0x180020a70  lea     r8, aReadlegacyprof; "ReadLegacyProfiles: GetLUAPhonebookPath"...
0x180020a77  mov     edx, 0Ch; dwFlags
0x180020a7c  call    cs:__imp_TracePrintfExA
0x180020a82  mov     rdi, [rsp+58h+arg_0]
0x180020a87  jmp     short loc_180020A3D
0x180020a89  mov     ecx, cs:g_dwTraceId
0x180020a8f  cmp     ecx, r12d
0x180020a92  jz      short loc_180020A3D
0x180020a94  lea     r8, aReadlegacyprof_2; "ReadLegacyProfiles: ReadRasFile for hid"...
0x180020a9b  jmp     loc_1800209B3
0x180020aa0  mov     ecx, cs:g_dwTraceId
0x180020aa6  cmp     ecx, r12d
0x180020aa9  jz      short loc_180020A3D
0x180020aab  lea     r8, aReadlegacyprof_0; "ReadLegacyProfiles: Syncmasterpbk faile"...
0x180020ab2  jmp     loc_1800209B3
```
