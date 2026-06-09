# DoInstallPackage(ushort const *,ushort const *,tagINSTALLUILEVEL)

- ea: `0x140004ca8`
- end: `0x140004ff4`
- name: `?DoInstallPackage@@YAHPEBG0W4tagINSTALLUILEVEL@@@Z`
- size: `844`
- prototype: `__int64 __fastcall(WCHAR *, const unsigned __int16 *, INSTALLUILEVEL)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003e10`
- `0x140006300`
- `0x140006e10`
- `0x140008b10`

## callees

- `0x140003ffc`
- `0x1400042b4`
- `0x140004ca8`
- `0x140005084`
- `0x1400086f8`
- `0x140009820`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x140004d4d`
- `KERNEL32!lstrlenW` at `0x140004d58`
- `KERNEL32!lstrlenW` at `0x140004d67`
- `KERNEL32!lstrlenW` at `0x140004d76`
- `KERNEL32!lstrlenW` at `0x140004e97`
- `KERNEL32!lstrlenW` at `0x140004ea2`
- `KERNEL32!lstrlenW` at `0x140004d4d`
- `KERNEL32!lstrlenW` at `0x140004d58`
- `KERNEL32!lstrlenW` at `0x140004d67`
- `KERNEL32!lstrlenW` at `0x140004d76`
- `KERNEL32!lstrlenW` at `0x140004e97`
- `KERNEL32!lstrlenW` at `0x140004ea2`
- `KERNEL32!GlobalAlloc` at `0x140004d9b`
- `KERNEL32!GlobalAlloc` at `0x140004ec7`
- `KERNEL32!GlobalAlloc` at `0x140004d9b`
- `KERNEL32!GlobalAlloc` at `0x140004ec7`
- `KERNEL32!GlobalFree` at `0x140004dba`
- `KERNEL32!GlobalFree` at `0x140004e0b`
- `KERNEL32!GlobalFree` at `0x140004e62`
- `KERNEL32!GlobalFree` at `0x140004f2a`
- `KERNEL32!GlobalFree` at `0x140004fe7`
- `KERNEL32!GlobalFree` at `0x140004dba`
- `KERNEL32!GlobalFree` at `0x140004e0b`
- `KERNEL32!GlobalFree` at `0x140004e62`
- `KERNEL32!GlobalFree` at `0x140004f2a`
- `KERNEL32!GlobalFree` at `0x140004fe7`
- `msi!__imp_MsiInstallProductW` at `0x140004f7f`
- `msi!__imp_MsiInstallProductW` at `0x140004fb1`
- `msi!__imp_MsiInstallProductW` at `0x140004f7f`
- `msi!__imp_MsiInstallProductW` at `0x140004fb1`
- `msi!__imp_MsiSetInternalUI` at `0x140004d07`
- `msi!__imp_MsiSetInternalUI` at `0x140004d07`

## string_xrefs

- `0x140004d25`: ` MSIINSTANCEGUID=`

## pseudocode

```c
__int64 __fastcall DoInstallPackage(WCHAR *a1, const unsigned __int16 *a2, INSTALLUILEVEL a3)
{
  int v5; // edi
  int v6; // edi
  int v7; // edi
  int v8; // edi
  __int64 *v9; // rax
  __int64 *v10; // r8
  WCHAR *v11; // rbx
  WCHAR *v13; // rax
  int v14; // edx
  int v15; // ebx
  int v16; // edi
  __int64 *v17; // rax
  __int64 *v18; // r8
  WCHAR *v19; // rbx
  WCHAR *v20; // rax
  int v21; // edx
  __int64 v22; // rdx
  UINT v23; // ebx
  HGLOBAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+2Ch] [rbp-D4h]
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String[20]; // [rsp+240h] [rbp+140h] BYREF

  hMem = &v27;
  if ( g_INSTALLUILEVEL != -1 )
    a3 = g_INSTALLUILEVEL;
  v25 = 260;
  MsiSetInternalUI(a3, 0);
  if ( g_szInstanceToConfigure )
  {
    wcscpy(String, L" MSIINSTANCEGUID=");
    v5 = lstrlenW(g_szCommandLine);
    v6 = lstrlenW(a2) + v5;
    v7 = lstrlenW(&g_szInstanceToConfigure) + v6;
    v8 = lstrlenW(String) + v7 + 2;
    if ( v8 <= 1024 )
    {
      v11 = (WCHAR *)qword_14000F0D0;
      v10 = qword_14000F0D0;
    }
    else
    {
      v9 = (__int64 *)GlobalAlloc(0x40u, 2LL * v8);
      v10 = v9;
      if ( !v9 )
        return 14;
      v11 = (WCHAR *)v9;
    }
    v13 = (WCHAR *)g_szCommandLine;
    if ( g_szCommandLine != v11 )
    {
      v14 = dword_14000F0C8;
      if ( v8 < dword_14000F0C8 )
        v14 = v8;
      for ( ; v14; v13 = (WCHAR *)g_szCommandLine )
      {
        --v14;
        *((_WORD *)v10 + v14) = v13[v14];
      }
    }
    if ( v13 != (WCHAR *)qword_14000F0D0 )
      GlobalFree(v13);
    g_szCommandLine = v11;
    dword_14000F0C8 = v8;
    if ( StringCchCatW(v11, v8, String) < 0
      || StringCchCatW((unsigned __int16 *)g_szCommandLine, dword_14000F0C8, &g_szInstanceToConfigure) < 0 )
    {
      goto LABEL_18;
    }
    goto LABEL_24;
  }
  v15 = lstrlenW(g_szCommandLine);
  v16 = v15 + lstrlenW(a2) + 2;
  if ( v16 <= 1024 )
  {
    v19 = (WCHAR *)qword_14000F0D0;
    v18 = qword_14000F0D0;
  }
  else
  {
    v17 = (__int64 *)GlobalAlloc(0x40u, 2LL * v16);
    v18 = v17;
    if ( !v17 )
    {
LABEL_24:
      v16 = dword_14000F0C8;
      v19 = (WCHAR *)g_szCommandLine;
      goto LABEL_34;
    }
    v19 = (WCHAR *)v17;
  }
  v20 = (WCHAR *)g_szCommandLine;
  if ( g_szCommandLine != v19 )
  {
    v21 = dword_14000F0C8;
    if ( v16 < dword_14000F0C8 )
      v21 = v16;
    for ( ; v21; v20 = (WCHAR *)g_szCommandLine )
    {
      --v21;
      *((_WORD *)v18 + v21) = v20[v21];
    }
  }
  if ( v20 != (WCHAR *)qword_14000F0D0 )
    GlobalFree(v20);
  g_szCommandLine = v19;
  dword_14000F0C8 = v16;
LABEL_34:
  if ( StringCchCatW(v19, v16, L" ") < 0 || StringCchCatW((unsigned __int16 *)g_szCommandLine, dword_14000F0C8, a2) < 0 )
  {
LABEL_18:
    if ( v25 > 260 )
      GlobalFree(hMem);
    return 1627;
  }
  v23 = MsiInstallProductW(a1, g_szCommandLine);
  if ( v23 == 2 )
  {
    v26 = 260;
    if ( AppendExtension(a1, v22, (__int64)&hMem) )
    {
      a1 = (WCHAR *)hMem;
      v23 = MsiInstallProductW((LPCWSTR)hMem, g_szCommandLine);
    }
  }
  if ( byte_140010F60 )
  {
    ConfigureMIF(a1);
    GenerateMIF(v23);
  }
  if ( !v23 )
    v23 = 0x8000;
  if ( v25 > 260 )
    GlobalFree(hMem);
  return v23;
}

```

## disassembly

```asm
0x140004ca8  mov     [rsp-8+arg_18], rbx
0x140004cad  push    rbp
0x140004cae  push    rsi
0x140004caf  push    rdi
0x140004cb0  push    r12
0x140004cb2  push    r13
0x140004cb4  push    r14
0x140004cb6  push    r15
0x140004cb8  lea     rbp, [rsp-170h]
0x140004cc0  sub     rsp, 270h
0x140004cc7  mov     rax, cs:__security_cookie
0x140004cce  xor     rax, rsp
0x140004cd1  mov     [rbp+1A0h+var_38], rax
0x140004cd8  cmp     cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A, 0FFFFFFFFh; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x140004cdf  lea     rax, [rsp+2A0h+var_270]
0x140004ce4  mov     r15, rdx
0x140004ce7  mov     [rsp+2A0h+hMem], rax
0x140004cec  cmovnz  r8d, cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x140004cf4  mov     rsi, rcx
0x140004cf7  mov     r13d, 104h
0x140004cfd  mov     ecx, r8d; dwUILevel
0x140004d00  xor     edx, edx; phWnd
0x140004d02  mov     [rsp+2A0h+var_278], r13d
0x140004d07  call    cs:__imp_MsiSetInternalUI
0x140004d0d  mov     rcx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; lpString
0x140004d14  xor     r12d, r12d
0x140004d17  cmp     cs:?g_szInstanceToConfigure@@3PAGA, r12w; ushort near * g_szInstanceToConfigure
0x140004d1f  jz      loc_140004E97
0x140004d25  movups  xmm0, xmmword ptr cs:aMsiinstancegui; " MSIINSTANCEGUID="
0x140004d2c  mov     eax, dword ptr cs:aMsiinstancegui+20h; "="
0x140004d32  movups  xmm1, xmmword ptr cs:aMsiinstancegui+10h; "ANCEGUID="
0x140004d39  mov     [rbp+1A0h+var_40], eax
0x140004d3f  movups  xmmword ptr [rbp+1A0h+String], xmm0
0x140004d46  movups  [rbp+1A0h+var_50], xmm1
0x140004d4d  call    cs:__imp_lstrlenW
0x140004d53  mov     rcx, r15; lpString
0x140004d56  mov     edi, eax
0x140004d58  call    cs:__imp_lstrlenW
0x140004d5e  lea     rcx, ?g_szInstanceToConfigure@@3PAGA; lpString
0x140004d65  add     edi, eax
0x140004d67  call    cs:__imp_lstrlenW
0x140004d6d  lea     rcx, [rbp+1A0h+String]; lpString
0x140004d74  add     edi, eax
0x140004d76  call    cs:__imp_lstrlenW
0x140004d7c  add     edi, 2
0x140004d7f  lea     r14, qword_14000F0D0
0x140004d86  add     edi, eax
0x140004d88  cmp     edi, 400h
0x140004d8e  jle     short loc_140004DCA
0x140004d90  movsxd  rdx, edi
0x140004d93  lea     ecx, [r12+40h]; uFlags
0x140004d98  add     rdx, rdx; dwBytes
0x140004d9b  call    cs:__imp_GlobalAlloc
0x140004da1  mov     r8, rax
0x140004da4  test    rax, rax
0x140004da7  jz      short loc_140004DAE
0x140004da9  mov     rbx, rax
0x140004dac  jmp     short loc_140004DD0
0x140004dae  cmp     [rsp+2A0h+var_278], r13d
0x140004db3  jle     short loc_140004DC0
0x140004db5  mov     rcx, [rsp+2A0h+hMem]; hMem
0x140004dba  call    cs:__imp_GlobalFree
0x140004dc0  mov     eax, 0Eh
0x140004dc5  jmp     loc_140004E6D
0x140004dca  mov     rbx, r14
0x140004dcd  mov     r8, r14
0x140004dd0  mov     rax, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004dd7  cmp     rax, rbx
0x140004dda  jz      short loc_140004E03
0x140004ddc  mov     edx, cs:dword_14000F0C8
0x140004de2  cmp     edi, edx
0x140004de4  cmovl   edx, edi
0x140004de7  test    edx, edx
0x140004de9  jz      short loc_140004E03
0x140004deb  sub     edx, 1
0x140004dee  movsxd  rcx, edx
0x140004df1  movzx   eax, word ptr [rax+rcx*2]
0x140004df5  mov     [r8+rcx*2], ax
0x140004dfa  mov     rax, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004e01  jnz     short loc_140004DEB
0x140004e03  cmp     rax, r14
0x140004e06  jz      short loc_140004E11
0x140004e08  mov     rcx, rax; hMem
0x140004e0b  call    cs:__imp_GlobalFree
0x140004e11  movsxd  rdx, edi; unsigned __int64
0x140004e14  lea     r8, [rbp+1A0h+String]; unsigned __int16 *
0x140004e1b  mov     rcx, rbx; unsigned __int16 *
0x140004e1e  mov     cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A, rbx; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004e25  mov     cs:dword_14000F0C8, edi
0x140004e2b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004e30  test    eax, eax
0x140004e32  js      short loc_140004E56
0x140004e34  movsxd  rdx, cs:dword_14000F0C8; unsigned __int64
0x140004e3b  lea     r8, ?g_szInstanceToConfigure@@3PAGA; unsigned __int16 *
0x140004e42  mov     rcx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; unsigned __int16 *
0x140004e49  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004e4e  test    eax, eax
0x140004e50  jns     loc_140004EDA
0x140004e56  cmp     [rsp+2A0h+var_278], r13d
0x140004e5b  jle     short loc_140004E68
0x140004e5d  mov     rcx, [rsp+2A0h+hMem]; hMem
0x140004e62  call    cs:__imp_GlobalFree
0x140004e68  mov     eax, 65Bh
0x140004e6d  mov     rcx, [rbp+1A0h+var_38]
0x140004e74  xor     rcx, rsp; StackCookie
0x140004e77  call    __security_check_cookie
0x140004e7c  mov     rbx, [rsp+2A0h+arg_18]
0x140004e84  add     rsp, 270h
0x140004e8b  pop     r15
0x140004e8d  pop     r14
0x140004e8f  pop     r13
0x140004e91  pop     r12
0x140004e93  pop     rdi
0x140004e94  pop     rsi
0x140004e95  pop     rbp
0x140004e96  retn
0x140004e97  call    cs:__imp_lstrlenW
0x140004e9d  mov     rcx, r15; lpString
0x140004ea0  mov     ebx, eax
0x140004ea2  call    cs:__imp_lstrlenW
0x140004ea8  lea     r14, qword_14000F0D0
0x140004eaf  lea     edi, [rax+2]
0x140004eb2  add     edi, ebx
0x140004eb4  cmp     edi, 400h
0x140004eba  jle     short loc_140004EE9
0x140004ebc  movsxd  rdx, edi
0x140004ebf  mov     ecx, 40h ; '@'; uFlags
0x140004ec4  add     rdx, rdx; dwBytes
0x140004ec7  call    cs:__imp_GlobalAlloc
0x140004ecd  mov     r8, rax
0x140004ed0  test    rax, rax
0x140004ed3  jz      short loc_140004EDA
0x140004ed5  mov     rbx, rax
0x140004ed8  jmp     short loc_140004EEF
0x140004eda  mov     edi, cs:dword_14000F0C8
0x140004ee0  mov     rbx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004ee7  jmp     short loc_140004F3D
0x140004ee9  mov     rbx, r14
0x140004eec  mov     r8, r14
0x140004eef  mov     rax, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004ef6  cmp     rax, rbx
0x140004ef9  jz      short loc_140004F22
0x140004efb  mov     edx, cs:dword_14000F0C8
0x140004f01  cmp     edi, edx
0x140004f03  cmovl   edx, edi
0x140004f06  test    edx, edx
0x140004f08  jz      short loc_140004F22
0x140004f0a  sub     edx, 1
0x140004f0d  movsxd  rcx, edx
0x140004f10  movzx   eax, word ptr [rax+rcx*2]
0x140004f14  mov     [r8+rcx*2], ax
0x140004f19  mov     rax, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004f20  jnz     short loc_140004F0A
0x140004f22  cmp     rax, r14
0x140004f25  jz      short loc_140004F30
0x140004f27  mov     rcx, rax; hMem
0x140004f2a  call    cs:__imp_GlobalFree
0x140004f30  mov     cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A, rbx; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140004f37  mov     cs:dword_14000F0C8, edi
0x140004f3d  movsxd  rdx, edi; unsigned __int64
0x140004f40  lea     r8, asc_14000B91C; " "
0x140004f47  mov     rcx, rbx; unsigned __int16 *
0x140004f4a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004f4f  test    eax, eax
0x140004f51  js      loc_140004E56
0x140004f57  movsxd  rdx, cs:dword_14000F0C8; unsigned __int64
0x140004f5e  mov     r8, r15; unsigned __int16 *
0x140004f61  mov     rcx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; unsigned __int16 *
0x140004f68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004f6d  test    eax, eax
0x140004f6f  js      loc_140004E56
0x140004f75  mov     rdx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; szCommandLine
0x140004f7c  mov     rcx, rsi; szPackagePath
0x140004f7f  call    cs:__imp_MsiInstallProductW
0x140004f85  mov     ebx, eax
0x140004f87  cmp     eax, 2
0x140004f8a  jnz     short loc_140004FB9
0x140004f8c  lea     r8, [rsp+2A0h+hMem]
0x140004f91  mov     [rsp+2A0h+var_274], r13d
0x140004f96  mov     rcx, rsi; unsigned __int16 *
0x140004f99  call    ?AppendExtension@@YA?AW4Bool@@PEBG0AEAV?$CAPITempBufferRef@G@@@Z; AppendExtension(ushort const *,ushort const *,CAPITempBufferRef<ushort> &)
0x140004f9e  test    eax, eax
0x140004fa0  jz      short loc_140004FB9
0x140004fa2  mov     rsi, [rsp+2A0h+hMem]
0x140004fa7  mov     rdx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; szCommandLine
0x140004fae  mov     rcx, rsi; szPackagePath
0x140004fb1  call    cs:__imp_MsiInstallProductW
0x140004fb7  mov     ebx, eax
0x140004fb9  cmp     cs:byte_140010F60, r12b
0x140004fc0  jz      short loc_140004FD1
0x140004fc2  mov     rcx, rsi; lpWideCharStr
0x140004fc5  call    ?ConfigureMIF@@YAXPEBG@Z; ConfigureMIF(ushort const *)
0x140004fca  mov     ecx, ebx; dwMessageId
0x140004fcc  call    ?GenerateMIF@@YAXI@Z; GenerateMIF(uint)
0x140004fd1  test    ebx, ebx
0x140004fd3  mov     eax, 8000h
0x140004fd8  cmovz   ebx, eax
0x140004fdb  cmp     [rsp+2A0h+var_278], r13d
0x140004fe0  jle     short loc_140004FED
0x140004fe2  mov     rcx, [rsp+2A0h+hMem]; hMem
0x140004fe7  call    cs:__imp_GlobalFree
0x140004fed  mov     eax, ebx
0x140004fef  jmp     loc_140004E6D
```
