# _CreateNewFolderName(ushort *,ulong,CFtpDir *)

- ea: `0x1800226f0`
- end: `0x180022816`
- name: `?_CreateNewFolderName@@YAJPEAGKPEAVCFtpDir@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct CFtpDir *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800222ec`

## callees

- `0x180002240`
- `0x1800096c4`
- `0x1800226f0`
- `0x18002698c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180022732`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800227c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180022732`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800227c7`

## pseudocode

```c
__int64 __fastcall _CreateNewFolderName(unsigned __int16 *a1, __int64 a2, struct CFtpDir *a3)
{
  int v5; // edi
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-258h] BYREF
  _QWORD pData[3]; // [rsp+28h] [rbp-250h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-238h] BYREF

  Buffer[0] = 0;
  LoadStringW(g_hinst, 0x10Au, a1, 260);
  LODWORD(v9) = 0;
  v5 = 1;
  if ( a3 )
  {
    while ( 1 )
    {
      v6 = (_QWORD *)*((_QWORD *)a3 + 3);
      if ( !v6 )
        break;
      (*(void (__fastcall **)(_QWORD))(*v6 + 8LL))(*((_QWORD *)a3 + 3));
      v7 = v6[2];
      pData[0] = &v9;
      pData[1] = a1;
      DPA_EnumCallback(*(HDPA *)(v7 + 16), _ComparePidlAndFolderStr, pData);
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      if ( !(_DWORD)v9 )
        break;
      if ( !Buffer[0] )
        LoadStringW(g_hinst, 0x10Bu, Buffer, 260);
      StringCchPrintfW(a1, 0x104u, Buffer, (unsigned int)++v5, v9);
      LODWORD(v9) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800226f0  mov     [rsp+arg_8], rbx
0x1800226f5  push    rbp
0x1800226f6  push    rsi
0x1800226f7  push    rdi
0x1800226f8  sub     rsp, 260h
0x1800226ff  mov     rax, cs:__security_cookie
0x180022706  xor     rax, rsp
0x180022709  mov     [rsp+278h+var_28], rax
0x180022711  mov     r9d, 104h; cchBufferMax
0x180022717  mov     rbp, r8
0x18002271a  mov     rsi, rcx
0x18002271d  xor     eax, eax
0x18002271f  mov     r8, rcx; lpBuffer
0x180022722  mov     [rsp+278h+Buffer], ax
0x180022727  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18002272e  lea     edx, [r9+6]; uID
0x180022732  call    cs:__imp_LoadStringW
0x180022738  mov     dword ptr [rsp+278h+var_258], 0
0x180022740  mov     edi, 1
0x180022745  test    rbp, rbp
0x180022748  jz      loc_1800227F1
0x18002274e  mov     rbx, [rbp+18h]
0x180022752  test    rbx, rbx
0x180022755  jz      loc_1800227F1
0x18002275b  mov     rax, [rbx]
0x18002275e  mov     rcx, rbx
0x180022761  mov     rax, [rax+8]
0x180022765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002276a  mov     rcx, [rbx+10h]
0x18002276e  lea     rax, [rsp+278h+var_258]
0x180022773  mov     [rsp+278h+pData], rax
0x180022778  lea     r8, [rsp+278h+pData]; pData
0x18002277d  mov     [rsp+278h+var_248], rsi
0x180022782  lea     rdx, ?_ComparePidlAndFolderStr@@YAHPEBXPEAX@Z; pfnCB
0x180022789  mov     rcx, [rcx+10h]; hdpa
0x18002278d  call    DPA_EnumCallback
0x180022792  mov     rax, [rbx]
0x180022795  mov     rcx, rbx
0x180022798  mov     rax, [rax+10h]
0x18002279c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227a1  cmp     dword ptr [rsp+278h+var_258], 0
0x1800227a6  jz      short loc_1800227F1
0x1800227a8  xor     eax, eax
0x1800227aa  cmp     ax, [rsp+278h+Buffer]
0x1800227af  jnz     short loc_1800227CD
0x1800227b1  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800227b8  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x1800227bd  mov     r9d, 104h; cchBufferMax
0x1800227c3  lea     edx, [r9+7]; uID
0x1800227c7  call    cs:__imp_LoadStringW
0x1800227cd  inc     edi
0x1800227cf  lea     r8, [rsp+278h+Buffer]; unsigned __int16 *
0x1800227d4  mov     r9d, edi
0x1800227d7  mov     edx, 104h; unsigned __int64
0x1800227dc  mov     rcx, rsi; unsigned __int16 *
0x1800227df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800227e4  mov     dword ptr [rsp+278h+var_258], 0
0x1800227ec  jmp     loc_18002274E
0x1800227f1  xor     eax, eax
0x1800227f3  mov     rcx, [rsp+278h+var_28]
0x1800227fb  xor     rcx, rsp; StackCookie
0x1800227fe  call    __security_check_cookie
0x180022803  mov     rbx, [rsp+278h+arg_8]
0x18002280b  add     rsp, 260h
0x180022812  pop     rdi
0x180022813  pop     rsi
0x180022814  pop     rbp
0x180022815  retn
```
