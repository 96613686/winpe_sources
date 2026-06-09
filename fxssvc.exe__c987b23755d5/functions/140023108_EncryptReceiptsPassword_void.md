# EncryptReceiptsPassword(void)

- ea: `0x140023108`
- end: `0x1400232c9`
- name: `?EncryptReceiptsPassword@@YAXXZ`
- size: `449`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400236a0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140023108`
- `0x140065dbc`
- `0x1400708c4`
- `0x14007d2d0`
- `0x14007ed5c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140023287`
- `ADVAPI32!RegCloseKey` at `0x140023287`
- `ADVAPI32!RegDeleteValueW` at `0x14002324a`
- `ADVAPI32!RegDeleteValueW` at `0x14002324a`
- `KERNEL32!GetLastError` at `0x140023194`
- `KERNEL32!GetLastError` at `0x14002321b`
- `KERNEL32!GetLastError` at `0x140023194`
- `KERNEL32!GetLastError` at `0x14002321b`

## pseudocode

```c
void EncryptReceiptsPassword(void)
{
  HKEY v0; // rdi
  DWORD LastError; // eax
  _WORD *RegistrySecureString; // rbx
  DWORD v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  _BYTE *i; // rax
  __int64 v8; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  LODWORD(v8) = 0;
  v0 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Receipts", 0, 0x2001Fu);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
    }
    return;
  }
  RegistrySecureString = (_WORD *)GetRegistrySecureString(v0, (__int64)&v8);
  if ( (_DWORD)v8 != 1 )
  {
    if ( !(_DWORD)v8 )
    {
LABEL_17:
      v4 = RegDeleteValueW(v0, L"Password");
      if ( v4
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v4);
      }
      goto LABEL_22;
    }
    if ( !(unsigned int)SetRegistrySecureString(v0) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v3);
      }
      goto LABEL_17;
    }
  }
LABEL_22:
  RegCloseKey(v0);
  if ( RegistrySecureString )
  {
    v5 = -1;
    do
      ++v5;
    while ( RegistrySecureString[v5] );
    v6 = 2 * v5;
    for ( i = RegistrySecureString; v6; --v6 )
      *i++ = 0;
    pMemFree(RegistrySecureString);
  }
}

```

## disassembly

```asm
0x140023108  push    rbx
0x14002310a  push    rsi
0x14002310b  push    rdi
0x14002310c  push    r14
0x14002310e  sub     rsp, 38h
0x140023112  mov     rcx, cs:WPP_GLOBAL_Control
0x140023119  lea     r14, WPP_GLOBAL_Control
0x140023120  cmp     rcx, r14
0x140023123  jz      short loc_140023146
0x140023125  test    byte ptr [rcx+1Ch], 4
0x140023129  jz      short loc_140023146
0x14002312b  cmp     byte ptr [rcx+19h], 5
0x14002312f  jb      short loc_140023146
0x140023131  mov     rcx, [rcx+10h]
0x140023135  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x14002313c  mov     edx, 2Bh ; '+'
0x140023141  call    WPP_SF_
0x140023146  xor     esi, esi
0x140023148  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Receipts"
0x14002314f  mov     r9d, 2001Fh
0x140023155  mov     dword ptr [rsp+58h+arg_0], esi
0x140023159  xor     r8d, r8d
0x14002315c  mov     rcx, 0FFFFFFFF80000002h
0x140023163  call    OpenRegistryKey
0x140023168  mov     rdi, rax
0x14002316b  test    rax, rax
0x14002316e  jnz     short loc_1400231BC
0x140023170  mov     rax, cs:WPP_GLOBAL_Control
0x140023177  cmp     rax, r14
0x14002317a  jz      loc_1400232BF
0x140023180  test    byte ptr [rax+1Ch], 4
0x140023184  jz      loc_1400232BF
0x14002318a  cmp     byte ptr [rax+19h], 2
0x14002318e  jb      loc_1400232BF
0x140023194  call    cs:__imp_GetLastError
0x14002319a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400231a1  lea     edx, [rsi+2Ch]
0x1400231a4  mov     r9d, eax
0x1400231a7  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400231ae  mov     rcx, [rcx+10h]
0x1400231b2  call    WPP_SF_d
0x1400231b7  jmp     loc_1400232BF
0x1400231bc  lea     rax, [rsp+58h+arg_0]
0x1400231c1  xor     r8d, r8d
0x1400231c4  mov     rcx, rdi; hKey
0x1400231c7  mov     [rsp+58h+var_38], rax; __int64
0x1400231cc  call    GetRegistrySecureString
0x1400231d1  mov     rbx, rax
0x1400231d4  mov     eax, dword ptr [rsp+58h+arg_0]
0x1400231d8  cmp     eax, 1
0x1400231db  jz      loc_140023284
0x1400231e1  test    eax, eax
0x1400231e3  jz      short loc_140023240
0x1400231e5  test    rbx, rbx
0x1400231e8  lea     r8, Class
0x1400231ef  mov     rcx, rdi
0x1400231f2  cmovnz  r8, rbx
0x1400231f6  call    SetRegistrySecureString
0x1400231fb  test    eax, eax
0x1400231fd  jnz     loc_140023284
0x140023203  mov     rax, cs:WPP_GLOBAL_Control
0x14002320a  cmp     rax, r14
0x14002320d  jz      short loc_140023240
0x14002320f  test    byte ptr [rax+1Ch], 4
0x140023213  jz      short loc_140023240
0x140023215  cmp     byte ptr [rax+19h], 2
0x140023219  jb      short loc_140023240
0x14002321b  call    cs:__imp_GetLastError
0x140023221  mov     rcx, cs:WPP_GLOBAL_Control
0x140023228  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x14002322f  mov     edx, 2Dh ; '-'
0x140023234  mov     r9d, eax
0x140023237  mov     rcx, [rcx+10h]
0x14002323b  call    WPP_SF_d
0x140023240  lea     rdx, aPassword; "Password"
0x140023247  mov     rcx, rdi; hKey
0x14002324a  call    cs:__imp_RegDeleteValueW
0x140023250  test    eax, eax
0x140023252  jz      short loc_140023284
0x140023254  mov     rcx, cs:WPP_GLOBAL_Control
0x14002325b  cmp     rcx, r14
0x14002325e  jz      short loc_140023284
0x140023260  test    byte ptr [rcx+1Ch], 4
0x140023264  jz      short loc_140023284
0x140023266  cmp     byte ptr [rcx+19h], 2
0x14002326a  jb      short loc_140023284
0x14002326c  mov     rcx, [rcx+10h]
0x140023270  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023277  mov     edx, 2Eh ; '.'
0x14002327c  mov     r9d, eax
0x14002327f  call    WPP_SF_d
0x140023284  mov     rcx, rdi; hKey
0x140023287  call    cs:__imp_RegCloseKey
0x14002328d  test    rbx, rbx
0x140023290  jz      short loc_1400232BF
0x140023292  or      rax, 0FFFFFFFFFFFFFFFFh
0x140023296  inc     rax
0x140023299  cmp     [rbx+rax*2], si
0x14002329d  jnz     short loc_140023296
0x14002329f  lea     rcx, [rax+rax]
0x1400232a3  mov     rax, rbx
0x1400232a6  test    rcx, rcx
0x1400232a9  jz      short loc_1400232B7
0x1400232ab  mov     [rax], sil
0x1400232ae  inc     rax
0x1400232b1  sub     rcx, 1
0x1400232b5  jnz     short loc_1400232AB
0x1400232b7  mov     rcx, rbx; lpMem
0x1400232ba  call    pMemFree
0x1400232bf  add     rsp, 38h
0x1400232c3  pop     r14
0x1400232c5  pop     rdi
0x1400232c6  pop     rsi
0x1400232c7  pop     rbx
0x1400232c8  retn
```
