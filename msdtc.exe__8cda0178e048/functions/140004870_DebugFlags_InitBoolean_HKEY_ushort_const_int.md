# DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)

- ea: `0x140004870`
- end: `0x140004951`
- name: `?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z`
- size: `225`
- prototype: `void __fastcall(HKEY hKey, LPCWSTR lpValueName, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004a08`

## callees

- `0x140004870`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400048b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400048b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140004930`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140004930`

## pseudocode

```c
void __fastcall DebugFlags::InitBoolean(HKEY hKey, LPCWSTR lpValueName, int *a3)
{
  int v6; // eax
  bool v7; // cf
  DWORD cbData[4]; // [rsp+30h] [rbp-128h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-118h] BYREF

  cbData[0] = 240;
  if ( RegQueryValueExW(hKey, lpValueName, 0, 0, Data, cbData) )
  {
    v7 = *a3 != 0;
    *(_WORD *)&Data[2] = 0;
    *(_WORD *)Data = v7 ? 89 : 78;
    RegSetValueExW(hKey, lpValueName, 0, 1u, Data, 4u);
  }
  else if ( cbData[0] >= 2 )
  {
    v6 = *(_WORD *)Data & 0xFFDF;
    if ( v6 == 78 )
    {
      *a3 = 0;
    }
    else if ( v6 == 89 )
    {
      *a3 = 1;
    }
  }
}

```

## disassembly

```asm
0x140004870  push    rbx
0x140004872  push    rsi
0x140004873  push    rdi
0x140004874  sub     rsp, 140h
0x14000487b  mov     rax, cs:__security_cookie
0x140004882  xor     rax, rsp
0x140004885  mov     [rsp+158h+var_28], rax
0x14000488d  lea     rax, [rsp+158h+cbData]
0x140004892  mov     [rsp+158h+cbData], 0F0h
0x14000489a  mov     [rsp+158h+lpcbData], rax; lpcbData
0x14000489f  mov     rbx, r8
0x1400048a2  lea     rax, [rsp+158h+Data]
0x1400048a7  xor     r9d, r9d; lpType
0x1400048aa  xor     r8d, r8d; lpReserved
0x1400048ad  mov     [rsp+158h+lpData], rax; lpData
0x1400048b2  mov     rsi, rdx
0x1400048b5  mov     rdi, rcx
0x1400048b8  call    cs:__imp_RegQueryValueExW
0x1400048be  test    eax, eax
0x1400048c0  jnz     short loc_1400048F0
0x1400048c2  cmp     [rsp+158h+cbData], 2
0x1400048c7  jb      short loc_140004936
0x1400048c9  mov     eax, dword ptr [rsp+158h+Data]
0x1400048cd  mov     ecx, 4Eh ; 'N'
0x1400048d2  and     eax, 0FFDFh
0x1400048d7  cmp     eax, ecx
0x1400048d9  jz      short loc_1400048E8
0x1400048db  cmp     eax, 59h ; 'Y'
0x1400048de  jnz     short loc_140004936
0x1400048e0  mov     dword ptr [rbx], 1
0x1400048e6  jmp     short loc_140004936
0x1400048e8  mov     dword ptr [rbx], 0
0x1400048ee  jmp     short loc_140004936
0x1400048f0  mov     eax, [rbx]
0x1400048f2  mov     r9d, 1; dwType
0x1400048f8  neg     eax
0x1400048fa  mov     dword ptr [rsp+158h+lpcbData], 4; cbData
0x140004902  mov     rdx, rsi; lpValueName
0x140004905  mov     rcx, rdi; hKey
0x140004908  sbb     r8w, r8w
0x14000490c  xor     eax, eax
0x14000490e  and     r8w, 0Bh
0x140004913  mov     word ptr [rsp+158h+Data+2], ax
0x140004918  add     r8w, 4Eh ; 'N'
0x14000491d  lea     rax, [rsp+158h+Data]
0x140004922  mov     word ptr [rsp+158h+Data], r8w
0x140004928  xor     r8d, r8d; Reserved
0x14000492b  mov     [rsp+158h+lpData], rax; lpData
0x140004930  call    cs:__imp_RegSetValueExW
0x140004936  mov     rcx, [rsp+158h+var_28]
0x14000493e  xor     rcx, rsp; StackCookie
0x140004941  call    __security_check_cookie
0x140004946  add     rsp, 140h
0x14000494d  pop     rdi
0x14000494e  pop     rsi
0x14000494f  pop     rbx
0x140004950  retn
```
