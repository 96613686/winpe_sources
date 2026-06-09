# CSyncMLDPU::SetXMLContent(ushort const *,ulong,int)

- ea: `0x18001c2d4`
- end: `0x18001c5d2`
- name: `?SetXMLContent@CSyncMLDPU@@QEAAJPEBGKH@Z`
- size: `766`
- prototype: `__int64 __fastcall(CSyncMLDPU *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a0d0`

## callees

- `0x180007e80`
- `0x1800128e4`
- `0x18001bf2c`
- `0x18001c2d4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c4ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c4ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c47b`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001c46b`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001c50d`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001c46b`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001c50d`
- `XmlLite!CreateXmlWriter` at `0x18001c324`
- `XmlLite!CreateXmlWriter` at `0x18001c324`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001c345`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001c345`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18001c424`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18001c424`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18001c402`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18001c402`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001c43e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001c4e8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001c43e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001c4e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSyncMLDPU::SetXMLContent(CSyncMLDPU *this, const unsigned __int16 *a2, int a3)
{
  int HGlobalFromStream; // ebx
  DWORD LowPart; // r14d
  const char *v6; // rax
  unsigned int v7; // eax
  signed int LastError; // eax
  unsigned int v9; // esi
  unsigned __int16 *v10; // rax
  HGLOBAL v11; // rcx
  unsigned __int16 *v12; // rbx
  const char *v13; // rax
  int i; // eax
  CSyncMLCmd *v15; // rcx
  LPSTREAM ppstm; // [rsp+30h] [rbp-20h] BYREF
  ULARGE_INTEGER pui; // [rsp+38h] [rbp-18h] BYREF
  HGLOBAL phglobal[2]; // [rsp+40h] [rbp-10h] BYREF
  void *ppvObject; // [rsp+88h] [rbp+38h] BYREF
  SIZE_T uBytes; // [rsp+90h] [rbp+40h] BYREF
  int v22; // [rsp+98h] [rbp+48h] BYREF

  ppstm = 0;
  ppvObject = 0;
  phglobal[0] = 0;
  v22 = 0;
  if ( !a3 )
    return 0;
  HGlobalFromStream = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( HGlobalFromStream >= 0 )
  {
    HGlobalFromStream = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( HGlobalFromStream >= 0 )
    {
      if ( ppstm )
      {
        HGlobalFromStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 24LL))(ppvObject);
        if ( HGlobalFromStream >= 0 )
        {
          HGlobalFromStream = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvObject + 160LL))(
                                ppvObject,
                                *((_QWORD *)this + 34),
                                0);
          if ( HGlobalFromStream >= 0 )
          {
            HGlobalFromStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
            if ( HGlobalFromStream >= 0 )
            {
              phglobal[1] = 0;
              HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(
                                    ppstm,
                                    0,
                                    0,
                                    0);
              if ( HGlobalFromStream >= 0 )
              {
                pui.QuadPart = 0;
                HGlobalFromStream = IStream_Size(ppstm, &pui);
                if ( HGlobalFromStream >= 0 )
                {
                  LowPart = pui.LowPart;
                  HGlobalFromStream = GetHGlobalFromStream(ppstm, phglobal);
                  if ( HGlobalFromStream >= 0 )
                  {
                    v6 = (const char *)GlobalLock(phglobal[0]);
                    v7 = SafeMultiByteToWideChar(0xFDE9u, 8u, v6, LowPart, 0, 0);
                    if ( !v7 )
                    {
LABEL_12:
                      LastError = GetLastError();
                      HGlobalFromStream = LastError;
                      if ( LastError > 0 )
                        HGlobalFromStream = (unsigned __int16)LastError | 0x80070000;
                      goto LABEL_24;
                    }
                    v9 = v7 + 1;
                    if ( v7 + 1 < v7 )
                    {
                      HGlobalFromStream = -2147024362;
                    }
                    else
                    {
                      LODWORD(uBytes) = 0;
                      HGlobalFromStream = ULongLongToULong(2LL * v9, (unsigned int *)&uBytes);
                      if ( HGlobalFromStream >= 0 )
                      {
                        v10 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)uBytes);
                        v11 = phglobal[0];
                        v12 = v10;
                        *((_QWORD *)this + 42) = v10;
                        v13 = (const char *)GlobalLock(v11);
                        if ( SafeMultiByteToWideChar(0xFDE9u, 8u, v13, LowPart, v12, v9) )
                        {
                          for ( i = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 34) + 56LL))(
                                      *((_QWORD *)this + 34),
                                      &v22);
                                ;
                                i = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 34) + 48LL))(
                                      *((_QWORD *)this + 34),
                                      &v22) )
                          {
                            HGlobalFromStream = i;
                            if ( i < 0 )
                              break;
                            if ( v22 != 13 )
                            {
                              HGlobalFromStream = CSyncMLDPU::endElement(this, 0, 0, L"Data", 4);
                              goto LABEL_24;
                            }
                          }
                          goto LABEL_24;
                        }
                        goto LABEL_12;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_24:
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( HGlobalFromStream < 0 )
  {
    v15 = (CSyncMLCmd *)*((_QWORD *)this + 8);
    if ( v15 )
      CSyncMLCmd::SetContextualParsingHresult(v15, HGlobalFromStream);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c2d4  mov     [rsp-28h+arg_18], r9d
0x18001c2d9  mov     [rsp-28h+ppvObject], rdx
0x18001c2de  push    rbp
0x18001c2df  push    rbx
0x18001c2e0  push    rsi
0x18001c2e1  push    rdi
0x18001c2e2  push    r14
0x18001c2e4  mov     rbp, rsp
0x18001c2e7  sub     rsp, 50h
0x18001c2eb  mov     [rbp+ppstm], 0
0x18001c2f3  mov     rdi, rcx
0x18001c2f6  mov     [rbp+ppvObject], 0
0x18001c2fe  mov     [rbp+phglobal], 0
0x18001c306  mov     [rbp+arg_18], 0
0x18001c30d  test    r8d, r8d
0x18001c310  jz      loc_18001C5C4
0x18001c316  xor     r8d, r8d; pMalloc
0x18001c319  lea     rdx, [rbp+ppvObject]; ppvObject
0x18001c31d  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18001c324  call    cs:__imp_CreateXmlWriter
0x18001c32b  nop     dword ptr [rax+rax+00h]
0x18001c330  mov     ebx, eax
0x18001c332  test    eax, eax
0x18001c334  js      loc_18001C57B
0x18001c33a  lea     r8, [rbp+ppstm]; ppstm
0x18001c33e  mov     edx, 1; fDeleteOnRelease
0x18001c343  xor     ecx, ecx; hGlobal
0x18001c345  call    cs:__imp_CreateStreamOnHGlobal
0x18001c34c  nop     dword ptr [rax+rax+00h]
0x18001c351  mov     ebx, eax
0x18001c353  test    eax, eax
0x18001c355  js      loc_18001C57B
0x18001c35b  mov     rdx, [rbp+ppstm]
0x18001c35f  test    rdx, rdx
0x18001c362  jz      loc_18001C57B
0x18001c368  mov     rcx, [rbp+ppvObject]
0x18001c36c  mov     rax, [rcx]
0x18001c36f  mov     rax, [rax+18h]
0x18001c373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c378  mov     ebx, eax
0x18001c37a  test    eax, eax
0x18001c37c  js      loc_18001C57B
0x18001c382  mov     rcx, [rbp+ppvObject]
0x18001c386  xor     r8d, r8d
0x18001c389  mov     rdx, [rdi+110h]
0x18001c390  mov     rax, [rcx]
0x18001c393  mov     rax, [rax+0A0h]
0x18001c39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39f  mov     ebx, eax
0x18001c3a1  test    eax, eax
0x18001c3a3  js      loc_18001C57B
0x18001c3a9  mov     rcx, [rbp+ppvObject]
0x18001c3ad  mov     rax, [rcx]
0x18001c3b0  mov     rax, [rax+0F8h]
0x18001c3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3bc  mov     ebx, eax
0x18001c3be  test    eax, eax
0x18001c3c0  js      loc_18001C57B
0x18001c3c6  mov     rcx, [rbp+ppstm]
0x18001c3ca  xor     r9d, r9d
0x18001c3cd  mov     [rbp+var_8], 0
0x18001c3d5  xor     r8d, r8d
0x18001c3d8  mov     rdx, [rbp+var_8]
0x18001c3dc  mov     rax, [rcx]
0x18001c3df  mov     rax, [rax+28h]
0x18001c3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3e8  mov     ebx, eax
0x18001c3ea  test    eax, eax
0x18001c3ec  js      loc_18001C57B
0x18001c3f2  mov     rcx, [rbp+ppstm]; pstm
0x18001c3f6  lea     rdx, [rbp+pui]; pui
0x18001c3fa  mov     qword ptr [rbp+pui], 0
0x18001c402  call    cs:__imp_IStream_Size
0x18001c409  nop     dword ptr [rax+rax+00h]
0x18001c40e  mov     ebx, eax
0x18001c410  test    eax, eax
0x18001c412  js      loc_18001C57B
0x18001c418  mov     rcx, [rbp+ppstm]; pstm
0x18001c41c  lea     rdx, [rbp+phglobal]; phglobal
0x18001c420  mov     r14d, dword ptr [rbp+pui]
0x18001c424  call    cs:__imp_GetHGlobalFromStream
0x18001c42b  nop     dword ptr [rax+rax+00h]
0x18001c430  mov     ebx, eax
0x18001c432  test    eax, eax
0x18001c434  js      loc_18001C57B
0x18001c43a  mov     rcx, [rbp+phglobal]; hMem
0x18001c43e  call    cs:__imp_GlobalLock
0x18001c445  nop     dword ptr [rax+rax+00h]
0x18001c44a  mov     [rsp+50h+var_28], 0
0x18001c452  mov     r9d, r14d
0x18001c455  mov     r8, rax
0x18001c458  mov     qword ptr [rsp+50h+var_30], 0
0x18001c461  mov     edx, 8
0x18001c466  mov     ecx, 0FDE9h
0x18001c46b  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18001c472  nop     dword ptr [rax+rax+00h]
0x18001c477  test    eax, eax
0x18001c479  jnz     short loc_18001C49F
0x18001c47b  call    cs:__imp_GetLastError
0x18001c482  nop     dword ptr [rax+rax+00h]
0x18001c487  mov     ebx, eax
0x18001c489  test    eax, eax
0x18001c48b  jle     loc_18001C57B
0x18001c491  movzx   ebx, ax
0x18001c494  or      ebx, 80070000h
0x18001c49a  jmp     loc_18001C57B
0x18001c49f  lea     esi, [rax+1]
0x18001c4a2  cmp     esi, eax
0x18001c4a4  jb      loc_18001C576
0x18001c4aa  mov     ecx, esi
0x18001c4ac  lea     rdx, [rbp+uBytes]; unsigned int *
0x18001c4b0  add     rcx, rcx; unsigned __int64
0x18001c4b3  mov     dword ptr [rbp+uBytes], 0
0x18001c4ba  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001c4bf  mov     ebx, eax
0x18001c4c1  test    eax, eax
0x18001c4c3  js      loc_18001C57B
0x18001c4c9  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001c4cc  xor     ecx, ecx; uFlags
0x18001c4ce  call    cs:__imp_LocalAlloc
0x18001c4d5  nop     dword ptr [rax+rax+00h]
0x18001c4da  mov     rcx, [rbp+phglobal]; hMem
0x18001c4de  mov     rbx, rax
0x18001c4e1  mov     [rdi+150h], rax
0x18001c4e8  call    cs:__imp_GlobalLock
0x18001c4ef  nop     dword ptr [rax+rax+00h]
0x18001c4f4  mov     [rsp+50h+var_28], esi
0x18001c4f8  mov     r9d, r14d
0x18001c4fb  mov     r8, rax
0x18001c4fe  mov     qword ptr [rsp+50h+var_30], rbx
0x18001c503  mov     edx, 8
0x18001c508  mov     ecx, 0FDE9h
0x18001c50d  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18001c514  nop     dword ptr [rax+rax+00h]
0x18001c519  test    eax, eax
0x18001c51b  jz      loc_18001C47B
0x18001c521  mov     rcx, [rdi+110h]
0x18001c528  mov     rax, [rcx]
0x18001c52b  mov     rax, [rax+38h]
0x18001c52f  jmp     short loc_18001C545
0x18001c531  cmp     [rbp+arg_18], 0Dh
0x18001c535  jnz     short loc_18001C556
0x18001c537  mov     rcx, [rdi+110h]
0x18001c53e  mov     rax, [rcx]
0x18001c541  mov     rax, [rax+30h]
0x18001c545  lea     rdx, [rbp+arg_18]
0x18001c549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c54e  mov     ebx, eax
0x18001c550  test    eax, eax
0x18001c552  jns     short loc_18001C531
0x18001c554  jmp     short loc_18001C57B
0x18001c556  lea     r9, aData; "Data"
0x18001c55d  mov     [rsp+50h+var_30], 4; int
0x18001c565  xor     r8d, r8d; int
0x18001c568  xor     edx, edx; unsigned __int16 *
0x18001c56a  mov     rcx, rdi; this
0x18001c56d  call    ?endElement@CSyncMLDPU@@AEAAJPEBGH0H@Z; CSyncMLDPU::endElement(ushort const *,int,ushort const *,int)
0x18001c572  mov     ebx, eax
0x18001c574  jmp     short loc_18001C57B
0x18001c576  mov     ebx, 80070216h
0x18001c57b  mov     rcx, [rbp+ppvObject]
0x18001c57f  test    rcx, rcx
0x18001c582  jz      short loc_18001C598
0x18001c584  mov     rax, [rcx]
0x18001c587  mov     rax, [rax+10h]
0x18001c58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c590  mov     [rbp+ppvObject], 0
0x18001c598  mov     rdx, [rbp+ppstm]
0x18001c59c  test    rdx, rdx
0x18001c59f  jz      short loc_18001C5B0
0x18001c5a1  mov     rax, [rdx]
0x18001c5a4  mov     rcx, rdx
0x18001c5a7  mov     rax, [rax+10h]
0x18001c5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5b0  test    ebx, ebx
0x18001c5b2  jns     short loc_18001C5C4
0x18001c5b4  mov     rcx, [rdi+40h]; this
0x18001c5b8  test    rcx, rcx
0x18001c5bb  jz      short loc_18001C5C4
0x18001c5bd  mov     edx, ebx; int
0x18001c5bf  call    ?SetContextualParsingHresult@CSyncMLCmd@@QEAAXJ@Z; CSyncMLCmd::SetContextualParsingHresult(long)
0x18001c5c4  xor     eax, eax
0x18001c5c6  add     rsp, 50h
0x18001c5ca  pop     r14
0x18001c5cc  pop     rdi
0x18001c5cd  pop     rsi
0x18001c5ce  pop     rbx
0x18001c5cf  pop     rbp
0x18001c5d0  retn
```
