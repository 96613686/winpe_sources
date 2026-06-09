# SaveDataObject(CMDBaseData *,CLocationWriter *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *)

- ea: `0x180023a74`
- end: `0x180023bd8`
- name: `?SaveDataObject@@YAJPEAVCMDBaseData@@PEAVCLocationWriter@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@@Z`
- size: `356`
- prototype: `int(struct CMDBaseData *, struct CLocationWriter *, struct IIS_CRYPTO_STORAGE *, struct _IIS_CRYPTO_BLOB *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005cd8`
- `0x1800246a4`
- `0x1800249b0`

## callees

- `0x180023a74`
- `0x18002e380`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180023b71`
- `ole32!CoTaskMemFree` at `0x180023b71`
- `IisRTL!PuDbgPrintW` at `0x180023bd0`
- `IisRTL!PuDbgPrintW` at `0x180023bd0`

## pseudocode

```c
__int64 __fastcall SaveDataObject(
        struct CMDBaseData *a1,
        struct CLocationWriter *a2,
        struct IIS_CRYPTO_STORAGE *a3,
        struct _IIS_CRYPTO_BLOB *a4)
{
  unsigned int v4; // edi
  __int64 v8; // rax
  unsigned __int8 *v9; // rsi
  unsigned int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  void *v13; // rcx
  unsigned int v15; // [rsp+28h] [rbp-30h]
  unsigned int v16; // [rsp+30h] [rbp-28h]
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = a4;
  v4 = 0;
  if ( (*((_BYTE *)a1 + 24) & 0x10) != 0 )
    return v4;
  if ( !(*(__int64 (__fastcall **)(struct CMDBaseData *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1) )
    return (unsigned int)-2147024882;
  v8 = *(_QWORD *)a1;
  pv = 0;
  v9 = (unsigned __int8 *)(*(__int64 (__fastcall **)(struct CMDBaseData *, __int64, _QWORD))(v8 + 24))(a1, 1, 0);
  v10 = (*(__int64 (__fastcall **)(struct CMDBaseData *, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, 1, 0);
  if ( (*((_BYTE *)a1 + 24) & 4) == 0 )
    goto LABEL_7;
  v4 = (**(__int64 (__fastcall ***)(struct IIS_CRYPTO_STORAGE *, LPVOID *, unsigned __int8 *, _QWORD, _DWORD))a3)(
         a3,
         &pv,
         v9,
         v10,
         0);
  if ( (v4 & 0x80000000) == 0 )
  {
    v9 = (unsigned __int8 *)pv;
    v10 = *((_DWORD *)pv + 1) + 8;
LABEL_7:
    v11 = (*(__int64 (__fastcall **)(struct CMDBaseData *))(*(_QWORD *)a1 + 8LL))(a1);
    v12 = CLocationWriter::AddProperty(a2, *((_DWORD *)a1 + 2), *((_DWORD *)a1 + 6), *((_DWORD *)a1 + 7), v11, v9, v10);
    v13 = pv;
    v4 = v12;
    if ( pv )
    {
      *(_BYTE *)pv = 88;
      CoTaskMemFree(v13);
    }
    return v4;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v16 = *((_DWORD *)a1 + 2);
    v15 = v4;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      9609,
      "SaveDataObject",
      L"[SaveDataObject] Unable to encrypt data. Failed with hr = 0x%x. Property id: %d Location %s.\n",
      v15,
      v16,
      *(_QWORD *)a2);
  }
  return v4;
}

```

## disassembly

```asm
0x180023a74  mov     [rsp+arg_0], rbx
0x180023a79  mov     [rsp+arg_8], rsi
0x180023a7e  mov     [rsp+pv], r9
0x180023a83  push    rdi
0x180023a84  push    r14
0x180023a86  push    r15
0x180023a88  sub     rsp, 40h
0x180023a8c  xor     edi, edi
0x180023a8e  mov     r15, r8
0x180023a91  test    byte ptr [rcx+18h], 10h
0x180023a95  mov     r14, rdx
0x180023a98  mov     rbx, rcx
0x180023a9b  jnz     loc_180023B77
0x180023aa1  mov     rax, [rcx]
0x180023aa4  xor     r8d, r8d
0x180023aa7  mov     rax, [rax+18h]
0x180023aab  lea     edi, [r8+1]
0x180023aaf  mov     edx, edi
0x180023ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ab6  test    rax, rax
0x180023ab9  jnz     short loc_180023AC5
0x180023abb  mov     edi, 8007000Eh
0x180023ac0  jmp     loc_180023B77
0x180023ac5  mov     rax, [rbx]
0x180023ac8  xor     r8d, r8d
0x180023acb  mov     edx, edi
0x180023acd  mov     [rsp+58h+pv], 0
0x180023ad6  mov     rcx, rbx
0x180023ad9  mov     rax, [rax+18h]
0x180023add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ae2  mov     rsi, rax
0x180023ae5  xor     r8d, r8d
0x180023ae8  mov     rax, [rbx]
0x180023aeb  mov     edx, edi
0x180023aed  mov     rcx, rbx
0x180023af0  mov     rax, [rax+20h]
0x180023af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023af9  test    byte ptr [rbx+18h], 4
0x180023afd  mov     edi, eax
0x180023aff  jz      short loc_180023B33
0x180023b01  mov     rax, [r15]
0x180023b04  lea     rdx, [rsp+58h+pv]
0x180023b09  mov     r9d, edi
0x180023b0c  mov     [rsp+58h+var_38], 0
0x180023b14  mov     r8, rsi
0x180023b17  mov     rcx, r15
0x180023b1a  mov     rax, [rax]
0x180023b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b22  mov     edi, eax
0x180023b24  test    eax, eax
0x180023b26  js      short loc_180023B8D
0x180023b28  mov     rsi, [rsp+58h+pv]
0x180023b2d  mov     edi, [rsi+4]
0x180023b30  add     edi, 8
0x180023b33  mov     rax, [rbx]
0x180023b36  mov     rcx, rbx
0x180023b39  mov     rax, [rax+8]
0x180023b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b42  mov     r9d, [rbx+1Ch]; unsigned int
0x180023b46  mov     rcx, r14; this
0x180023b49  mov     r8d, [rbx+18h]; unsigned int
0x180023b4d  mov     edx, [rbx+8]; unsigned int
0x180023b50  mov     [rsp+58h+var_28], edi; unsigned int
0x180023b54  mov     [rsp+58h+var_30], rsi; unsigned __int8 *
0x180023b59  mov     [rsp+58h+var_38], eax; unsigned int
0x180023b5d  call    ?AddProperty@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::AddProperty(ulong,ulong,ulong,ulong,uchar *,ulong)
0x180023b62  mov     rcx, [rsp+58h+pv]; pv
0x180023b67  mov     edi, eax
0x180023b69  test    rcx, rcx
0x180023b6c  jz      short loc_180023B77
0x180023b6e  mov     byte ptr [rcx], 58h ; 'X'
0x180023b71  call    cs:__imp_CoTaskMemFree
0x180023b77  mov     rbx, [rsp+58h+arg_0]
0x180023b7c  mov     eax, edi
0x180023b7e  mov     rsi, [rsp+58h+arg_8]
0x180023b83  add     rsp, 40h
0x180023b87  pop     r15
0x180023b89  pop     r14
0x180023b8b  pop     rdi
0x180023b8c  retn
0x180023b8d  test    byte ptr cs:g_dwDebugFlags, 3
0x180023b94  jz      short loc_180023B77
0x180023b96  mov     rax, [r14]
0x180023b99  lea     r9, aSavedataobject; "SaveDataObject"
0x180023ba0  mov     rcx, cs:g_pDebug
0x180023ba7  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180023bae  mov     [rsp+58h+var_20], rax
0x180023bb3  mov     r8d, 2589h
0x180023bb9  mov     eax, [rbx+8]
0x180023bbc  mov     [rsp+58h+var_28], eax
0x180023bc0  lea     rax, aSavedataobject_0; "[SaveDataObject] Unable to encrypt data"...
0x180023bc7  mov     dword ptr [rsp+58h+var_30], edi
0x180023bcb  mov     qword ptr [rsp+58h+var_38], rax
0x180023bd0  call    cs:__imp_PuDbgPrintW
0x180023bd6  jmp     short loc_180023B77
```
