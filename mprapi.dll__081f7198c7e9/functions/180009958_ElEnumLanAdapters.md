# ElEnumLanAdapters

- ea: `0x180009958`
- end: `0x180009d7c`
- name: `ElEnumLanAdapters`
- size: `1060`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a888`

## callees

- `0x1800098f4`
- `0x180009958`
- `0x180009d84`
- `0x180009fbc`
- `0x180017960`
- `0x180021d50`
- `0x18003f5e0`
- `0x18003f808`
- `0x18003f9c8`
- `0x180051112`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cfd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180009b04`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180009b04`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009ced`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009ced`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180009b4f`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180009b4f`

## pseudocode

```c
__int64 __fastcall ElEnumLanAdapters(unsigned __int16 *a1, __int64 a2, _QWORD *a3, unsigned int *a4, _DWORD *a5)
{
  _BYTE *v8; // r15
  void *v9; // r12
  unsigned int v10; // r13d
  __int64 result; // rax
  unsigned int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // r8
  const wchar_t *v15; // r10
  __int64 v16; // rdx
  WCHAR *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  WCHAR *v20; // rcx
  WCHAR *v21; // rax
  WCHAR *v22; // rcx
  unsigned __int16 *v23; // rcx
  int v24; // eax
  unsigned int v25; // r14d
  unsigned int v26; // esi
  HANDLE ProcessHeap; // rax
  void *v28; // rax
  size_t v29; // rbx
  LPVOID v30; // r14
  void *v31; // rbx
  HANDLE v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  HANDLE v35; // rax
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+30h] [rbp-D0h] BYREF
  int v38; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v39; // [rsp+38h] [rbp-C8h] BYREF
  DWORD nSize; // [rsp+3Ch] [rbp-C4h] BYREF
  LPVOID v41; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h]
  void *v43; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h]
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  void *Src[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v48; // [rsp+80h] [rbp-80h]
  WCHAR MachineName[512]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[512]; // [rsp+490h] [rbp+390h] BYREF

  v48 = a4;
  v44 = a3;
  phkResult = 0;
  nSize = 0;
  v8 = 0;
  v39 = 0;
  v9 = 0;
  lpMem = 0;
  v10 = 0;
  v45 = 0;
  v41 = 0;
  v38 = 0;
  v43 = 0;
  v37 = 0;
  if ( !a3 || !a4 || !a5 )
    return 87;
  *a5 = 0;
  *(_OWORD *)Src = 0;
  result = CheckMultiTenancy(a2, &v38);
  if ( (_DWORD)result )
    return result;
  if ( v38 )
  {
    v12 = ElEnumMultiTenantLanInterfaces(a2, &v43, &v37);
    v9 = v43;
    v10 = v37;
    v13 = v12;
    if ( v12 )
      goto LABEL_47;
  }
  v14 = 2147483646;
  v15 = L"\\\\";
  v16 = 512;
  v17 = MachineName;
  v18 = 2147483646;
  v19 = 512;
  do
  {
    if ( !v18 )
      break;
    if ( !*v15 )
      break;
    *v17++ = *v15++;
    --v18;
    --v19;
  }
  while ( v19 );
  v20 = v17 - 1;
  if ( v19 )
    v20 = v17;
  *v20 = 0;
  if ( a1 )
  {
    if ( *a1 == 92 )
    {
      v21 = MachineName;
      do
      {
        if ( !v14 )
          break;
        if ( !*a1 )
          break;
        *v21++ = *a1++;
        --v14;
        --v16;
      }
      while ( v16 );
      v22 = v21 - 1;
      if ( v16 )
        v22 = v21;
      *v22 = 0;
    }
    else
    {
      StringCbCatW(MachineName, 0x400u, a1);
    }
    v23 = MachineName;
  }
  else
  {
    nSize = 512;
    if ( !GetComputerNameW(Buffer, &nSize) )
      goto LABEL_46;
    StringCbCatW(MachineName, 0x400u, Buffer);
    v23 = 0;
  }
  v13 = WMICreateNamespaceString(v23);
  if ( v13 )
    goto LABEL_47;
  v13 = RegConnectRegistryW(MachineName, HKEY_LOCAL_MACHINE, &phkResult);
  if ( v13 )
    goto LABEL_47;
  v13 = IsNt40Machine(phkResult, a5);
  if ( v13 )
    goto LABEL_47;
  if ( *a5 )
  {
    v13 = 0;
    *v44 = 0;
    *a4 = 0;
    goto LABEL_47;
  }
  v24 = WMIConnect((unsigned __int16 *)lpMem, v36, (__int64)&v41);
  v8 = v41;
  if ( v24 < 0 || (int)WMIEnumLanAdapters(v45, Src, &v39, v41) < 0 )
  {
LABEL_46:
    v13 = 1003;
    goto LABEL_47;
  }
  v25 = v39;
  v26 = v39;
  if ( v38 )
    v26 = v39 + v10;
  if ( !v26 || v38 && v26 != v39 )
  {
    if ( v38 )
    {
      if ( 40 * (unsigned __int64)v26 > 0xFFFFFFFF )
        return 534;
      ProcessHeap = GetProcessHeap();
      v28 = HeapAlloc(ProcessHeap, 8u, 40 * v26);
      v41 = v28;
      if ( v28 )
      {
        v29 = 40LL * v25;
        memcpy_0(v28, Src[1], v29);
        v30 = v41;
        memcpy_0((char *)v41 + v29, v9, 40LL * v10);
        *v44 = v30;
        goto LABEL_44;
      }
      v13 = 8;
    }
LABEL_47:
    if ( Src[1] )
      ElCleanup(Src[1]);
    goto LABEL_49;
  }
  *v44 = Src[1];
LABEL_44:
  *v48 = v26;
LABEL_49:
  if ( v9 )
    ElCleanup(v9);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( dwDoUninitialize )
    CoUninitialize();
  if ( phkResult )
    RegCloseKey(phkResult);
  v31 = lpMem;
  if ( lpMem )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
  }
  if ( v8 )
  {
    v33 = 48;
    v34 = v8;
    do
    {
      *v34++ = 0;
      --v33;
    }
    while ( v33 );
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v8);
  }
  return v13;
}

```

## disassembly

```asm
0x180009958  push    rbp
0x18000995a  push    rbx
0x18000995b  push    rsi
0x18000995c  push    rdi
0x18000995d  push    r12
0x18000995f  push    r13
0x180009961  push    r14
0x180009963  push    r15
0x180009965  lea     rbp, [rsp-7A8h]
0x18000996d  sub     rsp, 8A8h
0x180009974  mov     rax, cs:__security_cookie
0x18000997b  xor     rax, rsp
0x18000997e  mov     [rbp+7E0h+var_50], rax
0x180009985  mov     rsi, [rbp+7E0h+arg_20]
0x18000998c  mov     rbx, rcx
0x18000998f  xor     ecx, ecx
0x180009991  mov     [rbp+7E0h+var_860], r9
0x180009995  mov     [rsp+8E0h+var_888], r8
0x18000999a  mov     r14, r9
0x18000999d  mov     [rsp+8E0h+phkResult], rcx
0x1800099a2  mov     rdi, rdx
0x1800099a5  mov     [rsp+8E0h+nSize], ecx
0x1800099a9  mov     r15d, ecx
0x1800099ac  mov     [rsp+8E0h+var_8A8], ecx
0x1800099b0  mov     r12d, ecx
0x1800099b3  mov     [rsp+8E0h+lpMem], rcx
0x1800099b8  mov     r13d, ecx
0x1800099bb  mov     [rsp+8E0h+var_880], rcx
0x1800099c0  mov     [rsp+8E0h+var_8A0], rcx
0x1800099c5  mov     [rsp+8E0h+var_8AC], ecx
0x1800099c9  mov     [rsp+8E0h+var_890], rcx
0x1800099ce  mov     [rsp+8E0h+var_8B0], ecx
0x1800099d2  test    r8, r8
0x1800099d5  jz      loc_180009D54
0x1800099db  test    r9, r9
0x1800099de  jz      loc_180009D54
0x1800099e4  test    rsi, rsi
0x1800099e7  jz      loc_180009D54
0x1800099ed  mov     [rsi], ecx
0x1800099ef  lea     rdx, [rsp+8E0h+var_8AC]
0x1800099f4  xorps   xmm0, xmm0
0x1800099f7  mov     rcx, rdi
0x1800099fa  movups  xmmword ptr [rsp+8E0h+Src], xmm0
0x1800099ff  call    CheckMultiTenancy
0x180009a04  xor     r11d, r11d
0x180009a07  test    eax, eax
0x180009a09  jnz     loc_180009D59
0x180009a0f  cmp     [rsp+8E0h+var_8AC], r11d
0x180009a14  jz      short loc_180009A42
0x180009a16  lea     r8, [rsp+8E0h+var_8B0]
0x180009a1b  mov     rcx, rdi
0x180009a1e  lea     rdx, [rsp+8E0h+var_890]
0x180009a23  call    ElEnumMultiTenantLanInterfaces
0x180009a28  mov     r12, [rsp+8E0h+var_890]
0x180009a2d  xor     r11d, r11d
0x180009a30  mov     r13d, [rsp+8E0h+var_8B0]
0x180009a35  mov     edi, eax
0x180009a37  test    eax, eax
0x180009a39  jz      short loc_180009A42
0x180009a3b  xor     ebx, ebx
0x180009a3d  jmp     loc_180009CAC
0x180009a42  mov     r8d, 7FFFFFFEh
0x180009a48  lea     r10, asc_18005910C; "\\\\"
0x180009a4f  mov     edx, 200h
0x180009a54  lea     rax, [rbp+7E0h+MachineName]
0x180009a58  mov     ecx, r8d
0x180009a5b  mov     r9d, edx
0x180009a5e  test    rcx, rcx
0x180009a61  jz      short loc_180009A8A
0x180009a63  movzx   r11d, word ptr [r10]
0x180009a67  test    r11w, r11w
0x180009a6b  jz      short loc_180009A87
0x180009a6d  mov     [rax], r11w
0x180009a71  add     r10, 2
0x180009a75  add     rax, 2
0x180009a79  xor     r11d, r11d
0x180009a7c  dec     rcx
0x180009a7f  sub     r9, 1
0x180009a83  jnz     short loc_180009A5E
0x180009a85  jmp     short loc_180009A8A
0x180009a87  xor     r11d, r11d
0x180009a8a  test    r9, r9
0x180009a8d  lea     rcx, [rax-2]
0x180009a91  cmovnz  rcx, rax
0x180009a95  mov     [rcx], r11w
0x180009a99  test    rbx, rbx
0x180009a9c  jz      short loc_180009AF4
0x180009a9e  cmp     word ptr [rbx], 5Ch ; '\'
0x180009aa2  jnz     short loc_180009ADB
0x180009aa4  lea     rax, [rbp+7E0h+MachineName]
0x180009aa8  test    r8, r8
0x180009aab  jz      short loc_180009AC9
0x180009aad  movzx   ecx, word ptr [rbx]
0x180009ab0  test    cx, cx
0x180009ab3  jz      short loc_180009AC9
0x180009ab5  mov     [rax], cx
0x180009ab8  add     rbx, 2
0x180009abc  add     rax, 2
0x180009ac0  dec     r8
0x180009ac3  sub     rdx, 1
0x180009ac7  jnz     short loc_180009AA8
0x180009ac9  xor     ebx, ebx
0x180009acb  lea     rcx, [rax-2]
0x180009acf  test    rdx, rdx
0x180009ad2  cmovnz  rcx, rax
0x180009ad6  mov     [rcx], bx
0x180009ad9  jmp     short loc_180009AEE
0x180009adb  mov     r8, rbx; unsigned __int16 *
0x180009ade  lea     rcx, [rbp+7E0h+MachineName]; unsigned __int16 *
0x180009ae2  mov     edx, 400h; unsigned __int64
0x180009ae7  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180009aec  xor     ebx, ebx
0x180009aee  lea     rcx, [rbp+7E0h+MachineName]
0x180009af2  jmp     short loc_180009B2B
0x180009af4  mov     [rsp+8E0h+nSize], edx
0x180009af8  lea     rcx, [rbp+7E0h+Buffer]; lpBuffer
0x180009aff  lea     rdx, [rsp+8E0h+nSize]; nSize
0x180009b04  call    cs:__imp_GetComputerNameW
0x180009b0a  xor     ebx, ebx
0x180009b0c  test    eax, eax
0x180009b0e  jz      loc_180009CA7
0x180009b14  lea     r8, [rbp+7E0h+Buffer]; unsigned __int16 *
0x180009b1b  mov     edx, 400h; unsigned __int64
0x180009b20  lea     rcx, [rbp+7E0h+MachineName]; unsigned __int16 *
0x180009b24  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180009b29  xor     ecx, ecx; unsigned __int16 *
0x180009b2b  lea     rdx, [rsp+8E0h+lpMem]
0x180009b30  call    WMICreateNamespaceString
0x180009b35  mov     edi, eax
0x180009b37  test    eax, eax
0x180009b39  jnz     loc_180009CAC
0x180009b3f  lea     r8, [rsp+8E0h+phkResult]; phkResult
0x180009b44  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180009b4b  lea     rcx, [rbp+7E0h+MachineName]; lpMachineName
0x180009b4f  call    cs:__imp_RegConnectRegistryW
0x180009b55  mov     edi, eax
0x180009b57  test    eax, eax
0x180009b59  jnz     loc_180009CAC
0x180009b5f  mov     rcx, [rsp+8E0h+phkResult]
0x180009b64  mov     rdx, rsi
0x180009b67  call    IsNt40Machine
0x180009b6c  mov     edi, eax
0x180009b6e  test    eax, eax
0x180009b70  jnz     loc_180009CAC
0x180009b76  cmp     [rsi], ebx
0x180009b78  jz      short loc_180009B8C
0x180009b7a  mov     rcx, [rsp+8E0h+var_888]
0x180009b7f  mov     edi, ebx
0x180009b81  mov     [rcx], rbx
0x180009b84  mov     [r14], ebx
0x180009b87  jmp     loc_180009CAC
0x180009b8c  mov     rcx, [rsp+8E0h+lpMem]; unsigned __int16 *
0x180009b91  lea     rax, [rsp+8E0h+var_8A0]
0x180009b96  lea     rdx, [rsp+8E0h+var_880]
0x180009b9b  mov     [rsp+8E0h+var_8B8], rax; __int64
0x180009ba0  call    WMIConnect
0x180009ba5  mov     r15, [rsp+8E0h+var_8A0]
0x180009baa  test    eax, eax
0x180009bac  js      loc_180009CA7
0x180009bb2  mov     rcx, [rsp+8E0h+var_880]
0x180009bb7  lea     r8, [rsp+8E0h+var_8A8]
0x180009bbc  mov     r9, r15
0x180009bbf  lea     rdx, [rsp+8E0h+Src]
0x180009bc4  call    WMIEnumLanAdapters
0x180009bc9  test    eax, eax
0x180009bcb  js      loc_180009CA7
0x180009bd1  mov     eax, [rsp+8E0h+var_8AC]
0x180009bd5  mov     r14d, [rsp+8E0h+var_8A8]
0x180009bda  mov     esi, r14d
0x180009bdd  test    eax, eax
0x180009bdf  jz      short loc_180009BE5
0x180009be1  lea     esi, [r14+r13]
0x180009be5  test    esi, esi
0x180009be7  jz      short loc_180009C04
0x180009be9  test    eax, eax
0x180009beb  jz      short loc_180009BF2
0x180009bed  cmp     esi, r14d
0x180009bf0  jnz     short loc_180009C04
0x180009bf2  mov     rcx, [rsp+8E0h+var_888]
0x180009bf7  mov     rax, [rsp+8E0h+Src+8]
0x180009bfc  mov     [rcx], rax
0x180009bff  jmp     loc_180009C95
0x180009c04  test    eax, eax
0x180009c06  jz      loc_180009CAC
0x180009c0c  mov     eax, esi
0x180009c0e  lea     rcx, [rax+rax*4]
0x180009c12  mov     eax, 0FFFFFFFFh
0x180009c17  shl     rcx, 3
0x180009c1b  cmp     rcx, rax
0x180009c1e  ja      short loc_180009C9D
0x180009c20  mov     ebx, ecx
0x180009c22  call    cs:__imp_GetProcessHeap
0x180009c28  mov     r8d, ebx; dwBytes
0x180009c2b  mov     edx, 8; dwFlags
0x180009c30  mov     rcx, rax; hHeap
0x180009c33  call    cs:__imp_HeapAlloc
0x180009c39  xor     ebx, ebx
0x180009c3b  mov     [rsp+8E0h+var_8A0], rax
0x180009c40  mov     r9, rax
0x180009c43  test    rax, rax
0x180009c46  jnz     short loc_180009C4D
0x180009c48  lea     edi, [rax+8]
0x180009c4b  jmp     short loc_180009CAC
0x180009c4d  mov     rdx, [rsp+8E0h+Src+8]; Src
0x180009c52  mov     eax, r14d
0x180009c55  lea     rcx, [rax+rax*4]
0x180009c59  lea     rbx, ds:0[rcx*8]
0x180009c61  mov     rcx, r9; void *
0x180009c64  mov     r8, rbx; Size
0x180009c67  call    memcpy_0
0x180009c6c  mov     r14, [rsp+8E0h+var_8A0]
0x180009c71  mov     rdx, r12; Src
0x180009c74  mov     eax, r13d
0x180009c77  lea     rcx, [rbx+r14]; void *
0x180009c7b  lea     r8, [rax+rax*4]
0x180009c7f  shl     r8, 3; Size
0x180009c83  call    memcpy_0
0x180009c88  mov     rcx, [rsp+8E0h+var_888]
0x180009c8d  xor     ebx, ebx
0x180009c8f  mov     r13d, ebx
0x180009c92  mov     [rcx], r14
0x180009c95  mov     rax, [rbp+7E0h+var_860]
0x180009c99  mov     [rax], esi
0x180009c9b  jmp     short loc_180009CBF
0x180009c9d  mov     eax, 216h
0x180009ca2  jmp     loc_180009D59
0x180009ca7  mov     edi, 3EBh
0x180009cac  mov     rcx, [rsp+8E0h+Src+8]; lpMem
0x180009cb1  test    rcx, rcx
0x180009cb4  jz      short loc_180009CBF
0x180009cb6  mov     edx, dword ptr [rsp+8E0h+Src]
0x180009cba  call    ElCleanup
0x180009cbf  test    r12, r12
0x180009cc2  jz      short loc_180009CCF
0x180009cc4  mov     edx, r13d
0x180009cc7  mov     rcx, r12; lpMem
0x180009cca  call    ElCleanup
0x180009ccf  mov     rcx, [rsp+8E0h+var_880]
0x180009cd4  test    rcx, rcx
0x180009cd7  jz      short loc_180009CE5
0x180009cd9  mov     rax, [rcx]
0x180009cdc  mov     rax, [rax+10h]
0x180009ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ce5  cmp     cs:?dwDoUninitialize@@3HA, ebx; int dwDoUninitialize
0x180009ceb  jz      short loc_180009CF3
0x180009ced  call    cs:__imp_CoUninitialize
0x180009cf3  mov     rcx, [rsp+8E0h+phkResult]; hKey
0x180009cf8  test    rcx, rcx
0x180009cfb  jz      short loc_180009D03
0x180009cfd  call    cs:__imp_RegCloseKey
0x180009d03  mov     rbx, [rsp+8E0h+lpMem]
0x180009d08  xor     esi, esi
0x180009d0a  test    rbx, rbx
0x180009d0d  jz      short loc_180009D23
0x180009d0f  call    cs:__imp_GetProcessHeap
0x180009d15  mov     r8, rbx; lpMem
0x180009d18  xor     edx, edx; dwFlags
0x180009d1a  mov     rcx, rax; hHeap
0x180009d1d  call    cs:__imp_HeapFree
0x180009d23  test    r15, r15
0x180009d26  jz      short loc_180009D50
0x180009d28  mov     ecx, 30h ; '0'
0x180009d2d  mov     rax, r15
0x180009d30  mov     [rax], sil
0x180009d33  inc     rax
0x180009d36  sub     rcx, 1
0x180009d3a  jnz     short loc_180009D30
0x180009d3c  call    cs:__imp_GetProcessHeap
0x180009d42  mov     r8, r15; lpMem
0x180009d45  xor     edx, edx; dwFlags
0x180009d47  mov     rcx, rax; hHeap
0x180009d4a  call    cs:__imp_HeapFree
0x180009d50  mov     eax, edi
0x180009d52  jmp     short loc_180009D59
0x180009d54  mov     eax, 57h ; 'W'
0x180009d59  mov     rcx, [rbp+7E0h+var_50]
0x180009d60  xor     rcx, rsp; StackCookie
0x180009d63  call    __security_check_cookie
0x180009d68  add     rsp, 8A8h
0x180009d6f  pop     r15
0x180009d71  pop     r14
0x180009d73  pop     r13
0x180009d75  pop     r12
0x180009d77  pop     rdi
0x180009d78  pop     rsi
0x180009d79  pop     rbx
0x180009d7a  pop     rbp
0x180009d7b  retn
```
