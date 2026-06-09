# CActiveXInstallBroker::UpdateDependencyList(HKEY__ *,ulong,ushort const * *)

- ea: `0x140006104`
- end: `0x1400061dc`
- name: `?UpdateDependencyList@CActiveXInstallBroker@@AEAAJPEAUHKEY__@@KPEAPEBG@Z`
- size: `216`
- prototype: `int(CActiveXInstallBroker *__hidden this, HKEY, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400061e4`

## callees

- `0x140006104`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000618a`
- `ADVAPI32!RegSetValueExW` at `0x14000618a`
- `ADVAPI32!RegCloseKey` at `0x1400061c0`
- `ADVAPI32!RegCloseKey` at `0x1400061c0`
- `ADVAPI32!RegCreateKeyW` at `0x140006148`
- `ADVAPI32!RegCreateKeyW` at `0x140006148`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::UpdateDependencyList(
        CActiveXInstallBroker *this,
        HKEY a2,
        unsigned int a3,
        const unsigned __int16 **a4)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  __int64 v6; // rdi
  int v10; // esi
  LSTATUS v11; // eax
  bool v12; // cc
  const WCHAR *v13; // rdx
  HKEY phkResult; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  phkResult = 0;
  v10 = 1;
  if ( !a3 )
    return v4;
  while ( 1 )
  {
    if ( v10 )
    {
      v11 = RegCreateKeyW(a2, L"Distribution Units", &phkResult);
      v12 = v11 <= 0;
      if ( v11 )
        goto LABEL_11;
      v5 = phkResult;
      v10 = 0;
    }
    if ( a4 )
    {
      v13 = a4[v6];
      if ( v13 )
        break;
    }
LABEL_9:
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= a3 )
      goto LABEL_15;
  }
  v11 = RegSetValueExW(v5, v13, 0, 1u, (const BYTE *)&Data, 1u);
  v12 = v11 <= 0;
  if ( !v11 )
  {
    v5 = phkResult;
    goto LABEL_9;
  }
LABEL_11:
  if ( v12 )
    v4 = v11;
  else
    v4 = (unsigned __int16)v11 | 0x80070000;
  v5 = phkResult;
LABEL_15:
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x140006104  mov     [rsp+phkResult], rcx
0x140006109  push    rbx
0x14000610a  push    rbp
0x14000610b  push    rsi
0x14000610c  push    rdi
0x14000610d  push    r14
0x14000610f  push    r15
0x140006111  sub     rsp, 38h
0x140006115  xor     ebx, ebx
0x140006117  xor     ecx, ecx
0x140006119  xor     edi, edi
0x14000611b  mov     [rsp+68h+phkResult], rcx
0x140006120  mov     r14, r9
0x140006123  mov     ebp, r8d
0x140006126  mov     r15, rdx
0x140006129  lea     esi, [rbx+1]
0x14000612c  test    r8d, r8d
0x14000612f  jz      loc_1400061CC
0x140006135  test    esi, esi
0x140006137  jz      short loc_14000615F
0x140006139  lea     r8, [rsp+68h+phkResult]; phkResult
0x14000613e  mov     rcx, r15; hKey
0x140006141  lea     rdx, aDistributionUn; "Distribution Units"
0x140006148  call    cs:__imp_RegCreateKeyW
0x14000614f  nop     dword ptr [rax+rax+00h]
0x140006154  test    eax, eax
0x140006156  jnz     short loc_1400061A7
0x140006158  mov     rcx, [rsp+68h+phkResult]; hKey
0x14000615d  xor     esi, esi
0x14000615f  test    r14, r14
0x140006162  jz      short loc_14000619F
0x140006164  mov     rdx, [r14+rdi*8]; lpValueName
0x140006168  test    rdx, rdx
0x14000616b  jz      short loc_14000619F
0x14000616d  lea     rax, Data
0x140006174  mov     [rsp+68h+cbData], 1; cbData
0x14000617c  mov     r9d, 1; dwType
0x140006182  mov     [rsp+68h+lpData], rax; lpData
0x140006187  xor     r8d, r8d; Reserved
0x14000618a  call    cs:__imp_RegSetValueExW
0x140006191  nop     dword ptr [rax+rax+00h]
0x140006196  test    eax, eax
0x140006198  jnz     short loc_1400061A7
0x14000619a  mov     rcx, [rsp+68h+phkResult]
0x14000619f  inc     edi
0x1400061a1  cmp     edi, ebp
0x1400061a3  jb      short loc_140006135
0x1400061a5  jmp     short loc_1400061BB
0x1400061a7  jg      short loc_1400061AD
0x1400061a9  mov     ebx, eax
0x1400061ab  jmp     short loc_1400061B6
0x1400061ad  movzx   ebx, ax
0x1400061b0  or      ebx, 80070000h
0x1400061b6  mov     rcx, [rsp+68h+phkResult]; hKey
0x1400061bb  test    rcx, rcx
0x1400061be  jz      short loc_1400061CC
0x1400061c0  call    cs:__imp_RegCloseKey
0x1400061c7  nop     dword ptr [rax+rax+00h]
0x1400061cc  mov     eax, ebx
0x1400061ce  add     rsp, 38h
0x1400061d2  pop     r15
0x1400061d4  pop     r14
0x1400061d6  pop     rdi
0x1400061d7  pop     rsi
0x1400061d8  pop     rbp
0x1400061d9  pop     rbx
0x1400061da  retn
```
