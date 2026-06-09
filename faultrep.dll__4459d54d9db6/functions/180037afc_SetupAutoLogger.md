# SetupAutoLogger

- ea: `0x180037afc`
- end: `0x180037d19`
- name: `SetupAutoLogger`
- size: `541`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180037e2c`

## callees

- `0x180037afc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037b63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037b63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d05`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037b9d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037bd3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037bfe`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037c29`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037c96`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037cc0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037ceb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037b9d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037bd3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037bfe`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037c29`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037c96`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037cc0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180037ceb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180037cfb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180037cfb`

## pseudocode

```c
LSTATUS __fastcall SetupAutoLogger(unsigned __int16 *a1)
{
  LSTATUS result; // eax
  HKEY v3; // rcx
  __int64 v4; // rax
  unsigned __int16 *v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // r8d
  const void *v8; // rcx
  int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD v10; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v10 = 0;
  Data = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\Microsoft-OCA-IPT",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &hKey,
             &v10);
  if ( !result )
  {
    v3 = hKey;
    if ( v10 == 2 )
      return RegCloseKey(v3);
    if ( RegSetKeyValueW(hKey, 0, L"BufferSize", 4u, a1 + 24, 4u)
      || RegSetKeyValueW(hKey, 0, L"Guid", 1u, L"{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}", 0x4Eu)
      || RegSetKeyValueW(hKey, 0, L"LogFileMode", 4u, a1 + 32, 4u)
      || RegSetKeyValueW(hKey, 0, L"MinimumBuffers", 4u, a1 + 26, 4u) )
    {
LABEL_17:
      RegDeleteKeyA(hKey, 0);
LABEL_18:
      v3 = hKey;
      return RegCloseKey(v3);
    }
    if ( *((int *)a1 + 18) < 0 )
    {
      v4 = a1[36];
      v5 = (unsigned __int16 *)((char *)a1 + v4 + 4);
      v6 = 0;
      v7 = *(unsigned __int16 *)((char *)a1 + v4 + 2);
      if ( *(unsigned __int16 *)((char *)a1 + v4 + 2) )
      {
        while ( v5[1] != 1 )
        {
          ++v6;
          v5 += 2 * *v5;
          if ( v6 >= v7 )
            goto LABEL_11;
        }
        goto LABEL_12;
      }
LABEL_11:
      if ( v6 < v7 )
      {
LABEL_12:
        v8 = v5 + 2;
LABEL_14:
        if ( !RegSetKeyValueW(hKey, 0, L"EnableKernelFlags", 3u, v8, 0x20u) )
        {
          Data = 0;
          if ( !RegSetKeyValueW(hKey, 0, L"Status", 4u, &Data, 4u) )
          {
            Data = 1;
            if ( !RegSetKeyValueW(hKey, 0, L"Start", 4u, &Data, 4u) )
              goto LABEL_18;
          }
        }
        goto LABEL_17;
      }
    }
    v8 = 0;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x180037afc  mov     r11, rsp
0x180037aff  mov     [r11+8], rbx
0x180037b03  push    rbp
0x180037b04  push    rsi
0x180037b05  push    r14
0x180037b07  mov     rbp, rsp
0x180037b0a  sub     rsp, 50h
0x180037b0e  lea     rax, [rbp+arg_10]
0x180037b12  mov     [rbp+hKey], 0
0x180037b1a  mov     [r11-28h], rax
0x180037b1e  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x180037b25  lea     rax, [rbp+hKey]
0x180037b29  mov     [rbp+arg_10], 0
0x180037b30  mov     [r11-30h], rax
0x180037b34  mov     rbx, rcx
0x180037b37  mov     qword ptr [r11-38h], 0
0x180037b3f  xor     r9d, r9d; lpClass
0x180037b42  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180037b4a  xor     r8d, r8d; Reserved
0x180037b4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037b54  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180037b5c  mov     [rbp+Data], 0
0x180037b63  call    cs:__imp_RegCreateKeyExW
0x180037b69  test    eax, eax
0x180037b6b  jnz     loc_180037D0B
0x180037b71  cmp     [rbp+arg_10], 2
0x180037b75  mov     rcx, [rbp+hKey]; hKey
0x180037b79  jz      loc_180037D05
0x180037b7f  mov     esi, 4
0x180037b84  lea     rax, [rbx+30h]
0x180037b88  mov     [rsp+50h+samDesired], esi; cbData
0x180037b8c  lea     r8, aBuffersize; "BufferSize"
0x180037b93  mov     r9d, esi; dwType
0x180037b96  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180037b9b  xor     edx, edx; lpSubKey
0x180037b9d  call    cs:__imp_RegSetKeyValueW
0x180037ba3  test    eax, eax
0x180037ba5  jnz     loc_180037CF5
0x180037bab  mov     rcx, [rbp+hKey]; hKey
0x180037baf  lea     rax, aC712af3dEd1e46; "{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}"
0x180037bb6  lea     r14d, [rsi-3]
0x180037bba  mov     [rsp+50h+samDesired], 4Eh ; 'N'; cbData
0x180037bc2  mov     r9d, r14d; dwType
0x180037bc5  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180037bca  lea     r8, aGuid; "Guid"
0x180037bd1  xor     edx, edx; lpSubKey
0x180037bd3  call    cs:__imp_RegSetKeyValueW
0x180037bd9  test    eax, eax
0x180037bdb  jnz     loc_180037CF5
0x180037be1  mov     rcx, [rbp+hKey]; hKey
0x180037be5  lea     rax, [rbx+40h]
0x180037be9  mov     [rsp+50h+samDesired], esi; cbData
0x180037bed  lea     r8, aLogfilemode; "LogFileMode"
0x180037bf4  mov     r9d, esi; dwType
0x180037bf7  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180037bfc  xor     edx, edx; lpSubKey
0x180037bfe  call    cs:__imp_RegSetKeyValueW
0x180037c04  test    eax, eax
0x180037c06  jnz     loc_180037CF5
0x180037c0c  mov     rcx, [rbp+hKey]; hKey
0x180037c10  lea     rax, [rbx+34h]
0x180037c14  mov     [rsp+50h+samDesired], esi; cbData
0x180037c18  lea     r8, aMinimumbuffers; "MinimumBuffers"
0x180037c1f  mov     r9d, esi; dwType
0x180037c22  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180037c27  xor     edx, edx; lpSubKey
0x180037c29  call    cs:__imp_RegSetKeyValueW
0x180037c2f  test    eax, eax
0x180037c31  jnz     loc_180037CF5
0x180037c37  cmp     [rbx+48h], eax
0x180037c3a  jge     short loc_180037C74
0x180037c3c  movzx   eax, word ptr [rbx+48h]
0x180037c40  lea     rcx, [rbx+4]
0x180037c44  add     rcx, rax
0x180037c47  xor     edx, edx
0x180037c49  movzx   r8d, word ptr [rax+rbx+2]
0x180037c4f  test    r8d, r8d
0x180037c52  jz      short loc_180037C6A
0x180037c54  cmp     [rcx+2], r14w
0x180037c59  jz      short loc_180037C6F
0x180037c5b  movzx   eax, word ptr [rcx]
0x180037c5e  add     edx, r14d
0x180037c61  lea     rcx, [rcx+rax*4]
0x180037c65  cmp     edx, r8d
0x180037c68  jb      short loc_180037C54
0x180037c6a  cmp     edx, r8d
0x180037c6d  jnb     short loc_180037C74
0x180037c6f  add     rcx, rsi
0x180037c72  jmp     short loc_180037C76
0x180037c74  xor     ecx, ecx
0x180037c76  mov     [rsp+50h+samDesired], 20h ; ' '; cbData
0x180037c7e  lea     r8, aEnablekernelfl; "EnableKernelFlags"
0x180037c85  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x180037c8a  mov     r9d, 3; dwType
0x180037c90  mov     rcx, [rbp+hKey]; hKey
0x180037c94  xor     edx, edx; lpSubKey
0x180037c96  call    cs:__imp_RegSetKeyValueW
0x180037c9c  test    eax, eax
0x180037c9e  jnz     short loc_180037CF5
0x180037ca0  mov     rcx, [rbp+hKey]; hKey
0x180037ca4  lea     r8, aStatus; "Status"
0x180037cab  mov     [rbp+Data], eax
0x180037cae  mov     r9d, esi; dwType
0x180037cb1  lea     rax, [rbp+Data]
0x180037cb5  mov     [rsp+50h+samDesired], esi; cbData
0x180037cb9  xor     edx, edx; lpSubKey
0x180037cbb  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180037cc0  call    cs:__imp_RegSetKeyValueW
0x180037cc6  test    eax, eax
0x180037cc8  jnz     short loc_180037CF5
0x180037cca  mov     rcx, [rbp+hKey]; hKey
0x180037cce  lea     rax, [rbp+Data]
0x180037cd2  mov     [rsp+50h+samDesired], esi; cbData
0x180037cd6  lea     r8, aStart; "Start"
0x180037cdd  mov     r9d, esi; dwType
0x180037ce0  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180037ce5  xor     edx, edx; lpSubKey
0x180037ce7  mov     [rbp+Data], r14d
0x180037ceb  call    cs:__imp_RegSetKeyValueW
0x180037cf1  test    eax, eax
0x180037cf3  jz      short loc_180037D01
0x180037cf5  mov     rcx, [rbp+hKey]; hKey
0x180037cf9  xor     edx, edx; lpSubKey
0x180037cfb  call    cs:__imp_RegDeleteKeyA
0x180037d01  mov     rcx, [rbp+hKey]; hKey
0x180037d05  call    cs:__imp_RegCloseKey
0x180037d0b  mov     rbx, [rsp+50h+arg_0]
0x180037d10  add     rsp, 50h
0x180037d14  pop     r14
0x180037d16  pop     rsi
0x180037d17  pop     rbp
0x180037d18  retn
```
