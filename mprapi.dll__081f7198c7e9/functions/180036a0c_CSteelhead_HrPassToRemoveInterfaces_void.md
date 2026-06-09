# CSteelhead::HrPassToRemoveInterfaces(void)

- ea: `0x180036a0c`
- end: `0x180036b7c`
- name: `?HrPassToRemoveInterfaces@CSteelhead@@IEAAJXZ`
- size: `368`
- prototype: `__int64 __fastcall(CSteelhead *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180036c94`

## callees

- `0x180023040`
- `0x180023e40`
- `0x180023f90`
- `0x180035b68`
- `0x180036870`
- `0x180036a0c`
- `0x180036e4c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180036ab4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180036ab4`
- `rtutils!TracePrintfW` at `0x180036b69`
- `rtutils!TracePrintfW` at `0x180036b69`

## string_xrefs

- `0x180036b5f`: `CSteelhead::HrPassToRemoveInterfaces`

## pseudocode

```c
__int64 __fastcall CSteelhead::HrPassToRemoveInterfaces(CSteelhead *this)
{
  unsigned int v2; // ebx
  signed int v3; // eax
  int v4; // ebp
  WCHAR *i; // rdi
  struct INetCfgComponent *v6; // rsi
  int v7; // eax
  const unsigned __int16 *v8; // r8
  struct INetCfgComponent *v10; // [rsp+70h] [rbp+8h] BYREF
  DWORD v11; // [rsp+78h] [rbp+10h] BYREF
  LPCWSTR lpString1; // [rsp+80h] [rbp+18h] BYREF

  lpString1 = 0;
  LODWORD(v10) = 0;
  v2 = 0;
  v3 = MprConfigInterfaceEnum(*((HANDLE *)this + 13), 0, (LPBYTE *)&lpString1, 0xFFFFFFFF, (LPDWORD)&v10, &v11, 0);
  if ( v3 )
  {
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    else
      v2 = v3;
    v4 = 0;
  }
  else
  {
    v4 = (int)v10;
  }
  if ( (v2 & 0x80000000) == 0 )
  {
    for ( i = (WCHAR *)lpString1; ; i += 276 )
    {
      if ( !v4 )
      {
        MprConfigBufferFree((LPVOID)lpString1);
        goto LABEL_26;
      }
      --v4;
      if ( *((_DWORD *)i + 133) == 4
        && (!*((_QWORD *)this + 5) || !*((_DWORD *)this + 284))
        && !(unsigned int)CSteelhead::IsIpv6TransportInstalled(this)
        && !lstrcmpW(i, (LPCWSTR)this + 56) )
      {
        break;
      }
      if ( *((_DWORD *)i + 133) != 3 )
        continue;
      v10 = 0;
      v7 = CSteelhead::FAdapterExistsWithMatchingBindName((struct INetCfg **)this, i, &v10);
      v6 = v10;
      if ( !v7 )
        goto LABEL_17;
      CSteelhead::HrPassToRemoveInterfaceTransports(this, (struct _MPR_INTERFACE_0 *)i, v8, v10);
LABEL_19:
      if ( v6 )
        ((void (__fastcall *)(struct INetCfgComponent *))v6->lpVtbl->Release)(v6);
    }
    v6 = 0;
LABEL_17:
    MprConfigInterfaceDelete(*((HANDLE *)this + 13), *((HANDLE *)i + 65));
    goto LABEL_19;
  }
  if ( v2 == -2147024637 )
  {
    v2 = 0;
LABEL_26:
    TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "CSteelhead::HrPassToRemoveInterfaces", v2);
  }
  else
  {
    TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "CSteelhead::HrPassToRemoveInterfaces", v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180036a0c  mov     r11, rsp
0x180036a0f  push    rbx
0x180036a10  push    rbp
0x180036a11  push    rsi
0x180036a12  push    rdi
0x180036a13  push    r14
0x180036a15  sub     rsp, 40h
0x180036a19  lea     rax, [r11+10h]
0x180036a1d  mov     qword ptr [r11+18h], 0
0x180036a25  mov     r14, rcx
0x180036a28  mov     dword ptr [rsp+68h+arg_0], 0
0x180036a30  mov     rcx, [rcx+68h]; hMprConfig
0x180036a34  lea     r8, [r11+18h]; lplpBuffer
0x180036a38  xor     ebx, ebx
0x180036a3a  or      r9d, 0FFFFFFFFh; dwPrefMaxLen
0x180036a3e  mov     [r11-38h], rbx
0x180036a42  xor     edx, edx; dwLevel
0x180036a44  mov     [r11-40h], rax
0x180036a48  lea     rax, [r11+8]
0x180036a4c  mov     [r11-48h], rax
0x180036a50  call    MprConfigInterfaceEnum
0x180036a55  test    eax, eax
0x180036a57  jz      short loc_180036A6C
0x180036a59  jg      short loc_180036A5F
0x180036a5b  mov     ebx, eax
0x180036a5d  jmp     short loc_180036A68
0x180036a5f  movzx   ebx, ax
0x180036a62  or      ebx, 80070000h
0x180036a68  xor     ebp, ebp
0x180036a6a  jmp     short loc_180036A70
0x180036a6c  mov     ebp, dword ptr [rsp+68h+arg_0]
0x180036a70  test    ebx, ebx
0x180036a72  js      loc_180036B3F
0x180036a78  mov     rdi, [rsp+68h+lpString1]
0x180036a80  jmp     loc_180036B28
0x180036a85  dec     ebp
0x180036a87  cmp     dword ptr [rdi+214h], 4
0x180036a8e  jnz     short loc_180036AC2
0x180036a90  cmp     qword ptr [r14+28h], 0
0x180036a95  jz      short loc_180036AA1
0x180036a97  cmp     dword ptr [r14+470h], 0
0x180036a9f  jnz     short loc_180036AC2
0x180036aa1  mov     rcx, r14; this
0x180036aa4  call    ?IsIpv6TransportInstalled@CSteelhead@@AEAAHXZ; CSteelhead::IsIpv6TransportInstalled(void)
0x180036aa9  test    eax, eax
0x180036aab  jnz     short loc_180036AC2
0x180036aad  lea     rdx, [r14+70h]; lpString2
0x180036ab1  mov     rcx, rdi; lpString1
0x180036ab4  call    cs:__imp_lstrcmpW
0x180036aba  test    eax, eax
0x180036abc  jnz     short loc_180036AC2
0x180036abe  xor     esi, esi
0x180036ac0  jmp     short loc_180036AED
0x180036ac2  cmp     dword ptr [rdi+214h], 3
0x180036ac9  jnz     short loc_180036B21
0x180036acb  lea     r8, [rsp+68h+arg_0]; struct INetCfgComponent **
0x180036ad0  mov     [rsp+68h+arg_0], 0
0x180036ad9  mov     rdx, rdi; unsigned __int16 *
0x180036adc  mov     rcx, r14; this
0x180036adf  call    ?FAdapterExistsWithMatchingBindName@CSteelhead@@IEAAHPEBGPEAPEAUINetCfgComponent@@@Z; CSteelhead::FAdapterExistsWithMatchingBindName(ushort const *,INetCfgComponent * *)
0x180036ae4  mov     rsi, [rsp+68h+arg_0]
0x180036ae9  test    eax, eax
0x180036aeb  jnz     short loc_180036AFF
0x180036aed  mov     rdx, [rdi+208h]; hRouterInterface
0x180036af4  mov     rcx, [r14+68h]; hMprConfig
0x180036af8  call    MprConfigInterfaceDelete
0x180036afd  jmp     short loc_180036B0D
0x180036aff  mov     r9, rsi; struct INetCfgComponent *
0x180036b02  mov     rdx, rdi; struct _MPR_INTERFACE_0 *
0x180036b05  mov     rcx, r14; this
0x180036b08  call    ?HrPassToRemoveInterfaceTransports@CSteelhead@@IEAAJPEAU_MPR_INTERFACE_0@@PEBGPEAUINetCfgComponent@@@Z; CSteelhead::HrPassToRemoveInterfaceTransports(_MPR_INTERFACE_0 *,ushort const *,INetCfgComponent *)
0x180036b0d  test    rsi, rsi
0x180036b10  jz      short loc_180036B21
0x180036b12  mov     rax, [rsi]
0x180036b15  mov     rcx, rsi
0x180036b18  mov     rax, [rax+10h]
0x180036b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b21  add     rdi, 228h
0x180036b28  test    ebp, ebp
0x180036b2a  jnz     loc_180036A85
0x180036b30  mov     rcx, [rsp+68h+lpString1]; pBuffer
0x180036b38  call    MprConfigBufferFree
0x180036b3d  jmp     short loc_180036B49
0x180036b3f  cmp     ebx, 80070103h
0x180036b45  jnz     short loc_180036B52
0x180036b47  xor     ebx, ebx
0x180036b49  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180036b50  jmp     short loc_180036B59
0x180036b52  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180036b59  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036b5f  lea     r8, aCsteelheadHrpa_1; "CSteelhead::HrPassToRemoveInterfaces"
0x180036b66  mov     r9d, ebx
0x180036b69  call    cs:__imp_TracePrintfW
0x180036b6f  mov     eax, ebx
0x180036b71  add     rsp, 40h
0x180036b75  pop     r14
0x180036b77  pop     rdi
0x180036b78  pop     rsi
0x180036b79  pop     rbp
0x180036b7a  pop     rbx
0x180036b7b  retn
```
