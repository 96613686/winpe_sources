# DsRolepCleanupOldNetlogonInformation

- ea: `0x18000c228`
- end: `0x18000c34a`
- name: `DsRolepCleanupOldNetlogonInformation`
- size: `290`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x18000c228`
- `0x18000d304`
- `0x18000d788`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c272`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c318`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c2e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c2e2`
- `ntdll!RtlFreeHeap` at `0x18000c335`
- `ntdll!RtlFreeHeap` at `0x18000c335`

## string_xrefs

- `0x18000c264`: `System\CurrentControlSet\services\Netlogon\parameters\`
- `0x18000c281`: `System\CurrentControlSet\services\Netlogon\parameters\`
- `0x18000c288`: `Failed to open %ws: %lu\n`
- `0x18000c2f8`: `Failed to delete registry key %ws: %lu\n`

## pseudocode

```c
__int64 DsRolepCleanupOldNetlogonInformation()
{
  void *v0; // rdi
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int NetlogonScriptsPath; // eax
  __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // esi
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  void *v9; // [rsp+58h] [rbp+10h]

  hKey = 0;
  v0 = 0;
  v9 = 0;
  DsRolepLogPrintRoutine(4, "Cleaning up old Netlogon information\n");
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\services\\Netlogon\\parameters\\",
         0,
         0x2001Fu,
         &hKey);
  v2 = v1;
  if ( v1 )
  {
    DsRolepLogPrintRoutine(
      1,
      "Failed to open %ws: %lu\n",
      L"System\\CurrentControlSet\\services\\Netlogon\\parameters\\",
      v1);
  }
  else
  {
    NetlogonScriptsPath = DsRolepGetNetlogonScriptsPath(hKey);
    v0 = v9;
    v2 = NetlogonScriptsPath;
    if ( NetlogonScriptsPath == 2 )
    {
      v2 = 0;
    }
    else
    {
      if ( !NetlogonScriptsPath )
      {
        v4 = -1;
        do
          ++v4;
        while ( *((_WORD *)v9 + v4) );
        v2 = DsRolepDelnodePath(v9, v4, 0);
      }
      v5 = RegDeleteValueW(hKey, L"Scripts");
      v6 = v5;
      if ( v5 )
        DsRolepLogPrintRoutine(1, "Failed to delete registry key %ws: %lu\n", L"Scripts", v5);
      if ( !v2 )
        v2 = v6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v0);
  return v2;
}

```

## disassembly

```asm
0x18000c228  mov     [rsp+arg_10], rbx
0x18000c22d  push    rbp
0x18000c22e  push    rsi
0x18000c22f  push    rdi
0x18000c230  sub     rsp, 30h
0x18000c234  xor     ebp, ebp
0x18000c236  lea     rdx, aCleaningUpOldN; "Cleaning up old Netlogon information\n"
0x18000c23d  mov     [rsp+48h+hKey], rbp
0x18000c242  mov     edi, ebp
0x18000c244  mov     [rsp+48h+arg_8], rbp
0x18000c249  lea     ecx, [rbp+4]
0x18000c24c  call    DsRolepLogPrintRoutine
0x18000c251  lea     rax, [rsp+48h+hKey]
0x18000c256  mov     r9d, 2001Fh; samDesired
0x18000c25c  xor     r8d, r8d; ulOptions
0x18000c25f  mov     [rsp+48h+phkResult], rax; phkResult
0x18000c264  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\services\\Ne"...
0x18000c26b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c272  call    cs:__imp_RegOpenKeyExW
0x18000c278  mov     ebx, eax
0x18000c27a  test    eax, eax
0x18000c27c  jz      short loc_18000C299
0x18000c27e  mov     r9d, eax
0x18000c281  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\services\\Ne"...
0x18000c288  lea     rdx, aFailedToOpenWs; "Failed to open %ws: %lu\n"
0x18000c28f  lea     ecx, [rbp+1]
0x18000c292  call    DsRolepLogPrintRoutine
0x18000c297  jmp     short loc_18000C30E
0x18000c299  mov     rcx, [rsp+48h+hKey]; hKey
0x18000c29e  lea     rdx, [rsp+48h+arg_8]
0x18000c2a3  call    DsRolepGetNetlogonScriptsPath
0x18000c2a8  mov     rdi, [rsp+48h+arg_8]
0x18000c2ad  mov     ebx, eax
0x18000c2af  cmp     eax, 2
0x18000c2b2  jnz     short loc_18000C2B8
0x18000c2b4  mov     ebx, ebp
0x18000c2b6  jmp     short loc_18000C30E
0x18000c2b8  test    eax, eax
0x18000c2ba  jnz     short loc_18000C2D6
0x18000c2bc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c2c0  inc     rdx
0x18000c2c3  cmp     [rdi+rdx*2], bp
0x18000c2c7  jnz     short loc_18000C2C0
0x18000c2c9  xor     r8d, r8d
0x18000c2cc  mov     rcx, rdi
0x18000c2cf  call    DsRolepDelnodePath
0x18000c2d4  mov     ebx, eax
0x18000c2d6  mov     rcx, [rsp+48h+hKey]; hKey
0x18000c2db  lea     rdx, aScripts; "Scripts"
0x18000c2e2  call    cs:__imp_RegDeleteValueW
0x18000c2e8  mov     esi, eax
0x18000c2ea  test    eax, eax
0x18000c2ec  jz      short loc_18000C309
0x18000c2ee  mov     r9d, eax
0x18000c2f1  lea     r8, aScripts; "Scripts"
0x18000c2f8  lea     rdx, aFailedToDelete_3; "Failed to delete registry key %ws: %lu"...
0x18000c2ff  mov     ecx, 1
0x18000c304  call    DsRolepLogPrintRoutine
0x18000c309  test    ebx, ebx
0x18000c30b  cmovz   ebx, esi
0x18000c30e  mov     rcx, [rsp+48h+hKey]; hKey
0x18000c313  test    rcx, rcx
0x18000c316  jz      short loc_18000C31E
0x18000c318  call    cs:__imp_RegCloseKey
0x18000c31e  test    rdi, rdi
0x18000c321  jz      short loc_18000C33B
0x18000c323  mov     rcx, gs:60h
0x18000c32c  mov     r8, rdi; P
0x18000c32f  xor     edx, edx; Flags
0x18000c331  mov     rcx, [rcx+30h]; HeapHandle
0x18000c335  call    cs:__imp_RtlFreeHeap
0x18000c33b  mov     eax, ebx
0x18000c33d  mov     rbx, [rsp+48h+arg_10]
0x18000c342  add     rsp, 30h
0x18000c346  pop     rdi
0x18000c347  pop     rsi
0x18000c348  pop     rbp
0x18000c349  retn
```
