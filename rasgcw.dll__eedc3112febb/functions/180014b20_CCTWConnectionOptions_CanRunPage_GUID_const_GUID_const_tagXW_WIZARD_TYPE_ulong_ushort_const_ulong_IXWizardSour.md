# CCTWConnectionOptions::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180014b20`
- end: `0x180014c12`
- name: `?CanRunPage@CCTWConnectionOptions@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014b20`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180014bd3`
- `rtutils!TracePrintfExA` at `0x180014c00`
- `rtutils!TracePrintfExA` at `0x180014bd3`
- `rtutils!TracePrintfExA` at `0x180014c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014b5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014b5b`

## pseudocode

```c
__int64 __fastcall CCTWConnectionOptions::CanRunPage(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  unsigned int v9; // edi
  __int128 v11; // xmm0
  char *v12; // rax
  char *v13; // rbx

  v9 = 0;
  *a9 = 0;
  v11 = *a2;
  *(_QWORD *)(a1 + 64) = a8;
  *(_OWORD *)(a1 + 72) = v11;
  if ( (a4 & 0x22) != 0 )
  {
    v12 = (char *)CoTaskMemAlloc(0x68u);
    v13 = v12;
    if ( v12 )
    {
      memset_0(v12 + 8, 0, 0x60u);
      *(_DWORD *)v13 = 104;
      *((_DWORD *)v13 + 1) = 4096;
      *((_QWORD *)v13 + 1) = hInst;
      *((_QWORD *)v13 + 5) = CCTWConnectionOptions::PageDlgProc;
      *((_QWORD *)v13 + 6) = a1;
      *((_QWORD *)v13 + 2) = 150;
      *((_QWORD *)v13 + 9) = 3029;
      *a9 = v13;
    }
    else
    {
      v9 = -2147024882;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x",
          -2147024882);
    }
  }
  else
  {
    v9 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v9;
}

```

## disassembly

```asm
0x180014b20  push    rbx
0x180014b22  push    rsi
0x180014b23  push    rdi
0x180014b24  push    r14
0x180014b26  sub     rsp, 38h
0x180014b2a  mov     r14, [rsp+58h+arg_40]
0x180014b32  xor     edi, edi
0x180014b34  mov     rax, [rsp+58h+arg_38]
0x180014b3c  mov     rsi, rcx
0x180014b3f  mov     [r14], rdi
0x180014b42  movups  xmm0, xmmword ptr [rdx]
0x180014b45  mov     [rcx+40h], rax
0x180014b49  movdqu  xmmword ptr [rcx+48h], xmm0
0x180014b4e  test    r9b, 22h
0x180014b52  jz      loc_180014BDB
0x180014b58  lea     ecx, [rdi+68h]; cb
0x180014b5b  call    cs:__imp_CoTaskMemAlloc
0x180014b61  mov     rbx, rax
0x180014b64  test    rax, rax
0x180014b67  jz      short loc_180014BB4
0x180014b69  lea     rcx, [rax+8]; void *
0x180014b6d  xor     edx, edx; Val
0x180014b6f  lea     r8d, [rdi+60h]; Size
0x180014b73  call    memset_0
0x180014b78  mov     dword ptr [rbx], 68h ; 'h'
0x180014b7e  lea     rax, ?PageDlgProc@CCTWConnectionOptions@@CAHPEAUHWND__@@I_K_J@Z; CCTWConnectionOptions::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180014b85  mov     dword ptr [rbx+4], 1000h
0x180014b8c  mov     rcx, cs:hInst
0x180014b93  mov     [rbx+8], rcx
0x180014b97  mov     [rbx+28h], rax
0x180014b9b  mov     [rbx+30h], rsi
0x180014b9f  mov     qword ptr [rbx+10h], 96h
0x180014ba7  mov     qword ptr [rbx+48h], 0BD5h
0x180014baf  mov     [r14], rbx
0x180014bb2  jmp     short loc_180014C06
0x180014bb4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014bba  mov     edi, 8007000Eh
0x180014bbf  cmp     ecx, 0FFFFFFFFh
0x180014bc2  jz      short loc_180014C06
0x180014bc4  mov     r9d, edi
0x180014bc7  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x180014bce  mov     edx, 0Ch; dwFlags
0x180014bd3  call    cs:__imp_TracePrintfExA
0x180014bd9  jmp     short loc_180014C06
0x180014bdb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014be1  mov     edi, 80004001h
0x180014be6  cmp     ecx, 0FFFFFFFFh
0x180014be9  jz      short loc_180014C06
0x180014beb  mov     [rsp+58h+var_30], edi
0x180014bef  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x180014bf6  mov     edx, 0Ch; dwFlags
0x180014bfb  mov     [rsp+58h+var_38], r9d
0x180014c00  call    cs:__imp_TracePrintfExA
0x180014c06  mov     eax, edi
0x180014c08  add     rsp, 38h
0x180014c0c  pop     r14
0x180014c0e  pop     rdi
0x180014c0f  pop     rsi
0x180014c10  pop     rbx
0x180014c11  retn
```
