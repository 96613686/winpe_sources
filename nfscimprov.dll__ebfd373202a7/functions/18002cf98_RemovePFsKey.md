# RemovePFsKey

- ea: `0x18002cf98`
- end: `0x18002d082`
- name: `RemovePFsKey`
- size: `234`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d088`

## callees

- `0x180001da6`
- `0x18002c964`
- `0x18002ca24`
- `0x18002cf98`
- `0x18002d258`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002d069`
- `KERNEL32!HeapFree` at `0x18002d069`
- `KERNEL32!HeapAlloc` at `0x18002cfd1`
- `KERNEL32!HeapAlloc` at `0x18002cfd1`
- `KERNEL32!GetProcessHeap` at `0x18002cfbf`
- `KERNEL32!GetProcessHeap` at `0x18002d05b`
- `KERNEL32!GetProcessHeap` at `0x18002cfbf`
- `KERNEL32!GetProcessHeap` at `0x18002d05b`
- `ADVAPI32!RegDeleteKeyExW` at `0x18002d018`
- `ADVAPI32!RegDeleteKeyExW` at `0x18002d018`
- `CLUSAPI!ClusterRegDeleteKey` at `0x18002d00a`
- `CLUSAPI!ClusterRegDeleteKey` at `0x18002d00a`

## pseudocode

```c
int __fastcall RemovePFsKey(HKEY hKey, const void **a2, char a3)
{
  __int64 v3; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  size_t v10; // rbx
  LONG v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  HANDLE v14; // rax
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v3 = *(unsigned __int16 *)a2;
  v16 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v3 + 2);
  v9 = v8;
  if ( v8 )
  {
    v10 = *(unsigned __int16 *)a2;
    memcpy_0(v8, a2[1], v10);
    v9[v10 >> 1] = 0;
    if ( a3 )
      v11 = ClusterRegDeleteKey(hKey, v9);
    else
      v11 = RegDeleteKeyExW(hKey, v9, 0, 0);
    if ( v11 && !(unsigned int)OpenPFsSubkeyFromComponent(hKey, (__int64)&v16) )
    {
      LOBYTE(v12) = a3;
      SetPFsTerminalNodeKeyValue(v16, v12, 0);
      LOBYTE(v13) = a3;
      NfsPFsCloseKey(v16, v13);
    }
    v14 = GetProcessHeap();
    LODWORD(v8) = HeapFree(v14, 0, v9);
  }
  return (int)v8;
}

```

## disassembly

```asm
0x18002cf98  mov     [rsp+arg_0], rbx
0x18002cf9d  mov     [rsp+arg_10], rbp
0x18002cfa2  push    rsi
0x18002cfa3  push    rdi
0x18002cfa4  push    r14
0x18002cfa6  sub     rsp, 30h
0x18002cfaa  movzx   ebx, word ptr [rdx]
0x18002cfad  mov     sil, r8b
0x18002cfb0  mov     rbp, rdx
0x18002cfb3  mov     [rsp+48h+arg_8], 0
0x18002cfbc  mov     r14, rcx
0x18002cfbf  call    cs:__imp_GetProcessHeap
0x18002cfc5  lea     r8, [rbx+2]; dwBytes
0x18002cfc9  mov     edx, 8; dwFlags
0x18002cfce  mov     rcx, rax; hHeap
0x18002cfd1  call    cs:__imp_HeapAlloc
0x18002cfd7  mov     rdi, rax
0x18002cfda  test    rax, rax
0x18002cfdd  jz      loc_18002D06F
0x18002cfe3  movzx   ebx, word ptr [rbp+0]
0x18002cfe7  mov     rcx, rax; void *
0x18002cfea  mov     rdx, [rbp+8]; Src
0x18002cfee  mov     r8d, ebx; Size
0x18002cff1  call    memcpy_0
0x18002cff6  xor     ecx, ecx
0x18002cff8  shr     rbx, 1
0x18002cffb  mov     rdx, rdi; lpSubKey
0x18002cffe  mov     [rdi+rbx*2], cx
0x18002d002  mov     rcx, r14; hKey
0x18002d005  test    sil, sil
0x18002d008  jz      short loc_18002D012
0x18002d00a  call    cs:__imp_ClusterRegDeleteKey
0x18002d010  jmp     short loc_18002D01E
0x18002d012  xor     r9d, r9d; Reserved
0x18002d015  xor     r8d, r8d; samDesired
0x18002d018  call    cs:__imp_RegDeleteKeyExW
0x18002d01e  test    eax, eax
0x18002d020  jz      short loc_18002D05B
0x18002d022  lea     rax, [rsp+48h+arg_8]
0x18002d027  mov     r8b, sil
0x18002d02a  mov     rdx, rbp
0x18002d02d  mov     [rsp+48h+var_28], rax; __int64
0x18002d032  mov     rcx, r14; hKey
0x18002d035  call    OpenPFsSubkeyFromComponent
0x18002d03a  test    eax, eax
0x18002d03c  jnz     short loc_18002D05B
0x18002d03e  mov     rcx, [rsp+48h+arg_8]
0x18002d043  xor     r8d, r8d
0x18002d046  mov     dl, sil
0x18002d049  call    SetPFsTerminalNodeKeyValue
0x18002d04e  mov     rcx, [rsp+48h+arg_8]
0x18002d053  mov     dl, sil
0x18002d056  call    NfsPFsCloseKey
0x18002d05b  call    cs:__imp_GetProcessHeap
0x18002d061  mov     r8, rdi; lpMem
0x18002d064  xor     edx, edx; dwFlags
0x18002d066  mov     rcx, rax; hHeap
0x18002d069  call    cs:__imp_HeapFree
0x18002d06f  mov     rbx, [rsp+48h+arg_0]
0x18002d074  mov     rbp, [rsp+48h+arg_10]
0x18002d079  add     rsp, 30h
0x18002d07d  pop     r14
0x18002d07f  pop     rdi
0x18002d080  pop     rsi
0x18002d081  retn
```
