# InitializeConnection

- ea: `0x180041d98`
- end: `0x180041f3f`
- name: `InitializeConnection`
- size: `423`
- prototype: `__int64 __fastcall(WCHAR *, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014e40`
- `0x180015030`

## callees

- `0x18003ccb8`
- `0x18003ce6c`
- `0x180041d98`
- `0x1800426ec`
- `0x180042bb0`
- `0x180043cc4`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180041ede`
- `RPCRT4!RpcBindingFree` at `0x180041ede`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041eb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ec7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180041e04`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180041e04`

## pseudocode

```c
__int64 __fastcall InitializeConnection(WCHAR *a1, _QWORD *a2)
{
  unsigned int RasmanDll; // ebx
  __int64 v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // rcx
  unsigned int Version; // eax
  char *v9; // rax
  char *v10; // r14
  wchar_t *v12; // rcx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-40h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+30h] [rbp-30h] BYREF
  WCHAR Buffer[8]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v18; // [rsp+48h] [rbp-18h]

  nSize = 16;
  Binding = 0;
  v14 = 0;
  *(_OWORD *)Buffer = 0;
  v18 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
    goto LABEL_18;
  if ( !a1 )
    goto LABEL_10;
  if ( *a1 == 92 && a1[1] == 92 )
  {
    a1 += 2;
  }
  else if ( !*a1 )
  {
LABEL_10:
    v6 = 1;
    a1 = Buffer;
    goto LABEL_11;
  }
  v6 = 0;
  if ( !(unsigned int)CompareStringWrapW(a1, Buffer) )
    goto LABEL_10;
LABEL_11:
  RasmanDll = LoadRasmanDll(v5);
  if ( !RasmanDll )
  {
    RasmanDll = LoadRasapi32Dll(v7);
    if ( !RasmanDll )
    {
      RasmanDll = ((__int64 (__fastcall *)(WCHAR *, RPC_BINDING_HANDLE *, _QWORD))g_pRasRpcBind)(a1, &Binding, v6);
      if ( !RasmanDll )
      {
        v14 = 6;
        Version = RemoteGetVersion(Binding, &v14);
        RasmanDll = Version;
        if ( Version == 1745 )
        {
          v14 = 4;
        }
        else if ( Version )
        {
          goto LABEL_19;
        }
        v9 = (char *)LocalAlloc(0x40u, 0x30u);
        v10 = v9;
        if ( !v9 )
        {
LABEL_18:
          RasmanDll = GetLastError();
          if ( !RasmanDll )
            return RasmanDll;
          goto LABEL_19;
        }
        v12 = (wchar_t *)(v9 + 16);
        *(_QWORD *)v9 = Binding;
        *((_DWORD *)v9 + 2) = v6;
        v13 = v14;
        if ( v6 )
          v13 = 6;
        *((_DWORD *)v10 + 3) = v13;
        RasmanDll = StringCchCopyWrapW(v12, 0x10u, a1);
        if ( !RasmanDll )
        {
          *a2 = v10;
          return RasmanDll;
        }
      }
    }
  }
LABEL_19:
  if ( Binding )
    RpcBindingFree(&Binding);
  return RasmanDll;
}

```

## disassembly

```asm
0x180041d98  mov     [rsp-28h+arg_10], rbx
0x180041d9d  mov     [rsp-28h+arg_18], rsi
0x180041da2  push    rbp
0x180041da3  push    rdi
0x180041da4  push    r13
0x180041da6  push    r14
0x180041da8  push    r15
0x180041daa  mov     rbp, rsp
0x180041dad  sub     rsp, 60h
0x180041db1  mov     rax, cs:__security_cookie
0x180041db8  xor     rax, rsp
0x180041dbb  mov     [rbp+var_8], rax
0x180041dbf  mov     [rbp+nSize], 10h
0x180041dc6  xorps   xmm0, xmm0
0x180041dc9  mov     [rbp+Binding], 0
0x180041dd1  mov     r15, rdx
0x180041dd4  mov     [rbp+var_40], 0
0x180041ddb  mov     rdi, rcx
0x180041dde  movups  xmmword ptr [rbp+Buffer], xmm0
0x180041de2  movups  [rbp+var_18], xmm0
0x180041de6  test    rdx, rdx
0x180041de9  jnz     short loc_180041DF5
0x180041deb  mov     ebx, 80070057h
0x180041df0  jmp     loc_180041EE4
0x180041df5  mov     qword ptr [rdx], 0
0x180041dfc  lea     rcx, [rbp+Buffer]; lpBuffer
0x180041e00  lea     rdx, [rbp+nSize]; nSize
0x180041e04  call    cs:__imp_GetComputerNameW
0x180041e0a  test    eax, eax
0x180041e0c  jz      loc_180041EC7
0x180041e12  test    rdi, rdi
0x180041e15  jz      short loc_180041E4B
0x180041e17  mov     eax, 5Ch ; '\'
0x180041e1c  cmp     [rdi], ax
0x180041e1f  jnz     short loc_180041E2D
0x180041e21  cmp     ax, [rdi+2]
0x180041e25  jnz     short loc_180041E2D
0x180041e27  add     rdi, 4
0x180041e2b  jmp     short loc_180041E39
0x180041e2d  test    rdi, rdi
0x180041e30  jz      short loc_180041E4B
0x180041e32  xor     eax, eax
0x180041e34  cmp     ax, [rdi]
0x180041e37  jz      short loc_180041E4B
0x180041e39  lea     rdx, [rbp+Buffer]; lpString2
0x180041e3d  mov     rcx, rdi; lpString1
0x180041e40  xor     esi, esi
0x180041e42  call    CompareStringWrapW
0x180041e47  test    eax, eax
0x180041e49  jnz     short loc_180041E54
0x180041e4b  mov     esi, 1
0x180041e50  lea     rdi, [rbp+Buffer]
0x180041e54  call    LoadRasmanDll
0x180041e59  mov     ebx, eax
0x180041e5b  test    eax, eax
0x180041e5d  jnz     short loc_180041ED3
0x180041e5f  call    LoadRasapi32Dll
0x180041e64  mov     ebx, eax
0x180041e66  test    eax, eax
0x180041e68  jnz     short loc_180041ED3
0x180041e6a  mov     rax, cs:g_pRasRpcBind
0x180041e71  lea     rdx, [rbp+Binding]
0x180041e75  mov     r8d, esi
0x180041e78  mov     rcx, rdi
0x180041e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e80  mov     ebx, eax
0x180041e82  test    eax, eax
0x180041e84  jnz     short loc_180041ED3
0x180041e86  mov     rcx, [rbp+Binding]
0x180041e8a  lea     r13d, [rax+6]
0x180041e8e  lea     rdx, [rbp+var_40]
0x180041e92  mov     [rbp+var_40], r13d
0x180041e96  call    RemoteGetVersion
0x180041e9b  mov     ebx, eax
0x180041e9d  cmp     eax, 6D1h
0x180041ea2  jnz     short loc_180041EAD
0x180041ea4  mov     [rbp+var_40], 4
0x180041eab  jmp     short loc_180041EB1
0x180041ead  test    eax, eax
0x180041eaf  jnz     short loc_180041ED3
0x180041eb1  mov     edx, 30h ; '0'; uBytes
0x180041eb6  lea     ecx, [rdx+10h]; uFlags
0x180041eb9  call    cs:__imp_LocalAlloc
0x180041ebf  mov     r14, rax
0x180041ec2  test    rax, rax
0x180041ec5  jnz     short loc_180041F0B
0x180041ec7  call    cs:__imp_GetLastError
0x180041ecd  mov     ebx, eax
0x180041ecf  test    eax, eax
0x180041ed1  jz      short loc_180041EE4
0x180041ed3  cmp     [rbp+Binding], 0
0x180041ed8  jz      short loc_180041EE4
0x180041eda  lea     rcx, [rbp+Binding]; Binding
0x180041ede  call    cs:__imp_RpcBindingFree
0x180041ee4  mov     eax, ebx
0x180041ee6  mov     rcx, [rbp+var_8]
0x180041eea  xor     rcx, rsp; StackCookie
0x180041eed  call    __security_check_cookie
0x180041ef2  lea     r11, [rsp+60h+var_s0]
0x180041ef7  mov     rbx, [r11+40h]
0x180041efb  mov     rsi, [r11+48h]
0x180041eff  mov     rsp, r11
0x180041f02  pop     r15
0x180041f04  pop     r14
0x180041f06  pop     r13
0x180041f08  pop     rdi
0x180041f09  pop     rbp
0x180041f0a  retn
0x180041f0b  mov     rax, [rbp+Binding]
0x180041f0f  lea     rcx, [r14+10h]
0x180041f13  mov     [r14], rax
0x180041f16  test    esi, esi
0x180041f18  mov     [r14+8], esi
0x180041f1c  mov     r8, rdi
0x180041f1f  mov     eax, [rbp+var_40]
0x180041f22  mov     edx, 10h
0x180041f27  cmovnz  eax, r13d
0x180041f2b  mov     [r14+0Ch], eax
0x180041f2f  call    StringCchCopyWrapW
0x180041f34  mov     ebx, eax
0x180041f36  test    eax, eax
0x180041f38  jnz     short loc_180041ED3
0x180041f3a  mov     [r15], r14
0x180041f3d  jmp     short loc_180041EE4
```
