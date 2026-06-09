# CIncomingConnectionCheckDevsPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180018c80`
- end: `0x180018d88`
- name: `?CanRunPage@CIncomingConnectionCheckDevsPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(CIncomingConnectionCheckDevsPage *, __int64, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180018c80`
- `0x180018d90`
- `0x180018eec`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180018d51`
- `rtutils!TracePrintfExA` at `0x180018d80`
- `rtutils!TracePrintfExA` at `0x180018d51`
- `rtutils!TracePrintfExA` at `0x180018d80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018cc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018cc6`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionCheckDevsPage::CanRunPage(
        CIncomingConnectionCheckDevsPage *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  int v11; // ebp
  char *v12; // rax
  char *v13; // rbx
  unsigned int v14; // ebx

  *a9 = 0;
  *((_QWORD *)a1 + 8) = a8;
  v11 = CIncomingConnectionCheckDevsPage::CheckDevices(a1);
  if ( v11 )
    goto LABEL_5;
  if ( (a4 & 0x22) != 0 )
  {
    v12 = (char *)CoTaskMemAlloc(0x68u);
    v13 = v12;
    if ( v12 )
    {
      memset_0(v12 + 8, 0, (unsigned int)(v11 + 96));
      *(_DWORD *)v13 = 104;
      *((_DWORD *)v13 + 1) = 4096;
      *((_QWORD *)v13 + 1) = hInst;
      *((_QWORD *)v13 + 5) = CIncomingConnectionCheckDevsPage::PageDlgProc;
      *((_QWORD *)v13 + 6) = a1;
      *((_QWORD *)v13 + 2) = 131;
      *((_QWORD *)v13 + 9) = 3060;
      *a9 = v13;
LABEL_5:
      v14 = 0;
      CIncomingConnectionCheckDevsPage::UpdateDevicePresenceInPropertyBag(a1, v11);
      return v14;
    }
    v14 = -2147024882;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x", -2147024882);
  }
  else
  {
    v14 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v14;
}

```

## disassembly

```asm
0x180018c80  push    rbx
0x180018c82  push    rbp
0x180018c83  push    rsi
0x180018c84  push    rdi
0x180018c85  push    r14
0x180018c87  sub     rsp, 30h
0x180018c8b  mov     rax, [rsp+58h+arg_38]
0x180018c93  mov     edi, r9d
0x180018c96  mov     r14, [rsp+58h+arg_40]
0x180018c9e  mov     rsi, rcx
0x180018ca1  mov     qword ptr [r14], 0
0x180018ca8  mov     [rcx+40h], rax
0x180018cac  call    ?CheckDevices@CIncomingConnectionCheckDevsPage@@AEAAHXZ; CIncomingConnectionCheckDevsPage::CheckDevices(void)
0x180018cb1  mov     ebp, eax
0x180018cb3  test    eax, eax
0x180018cb5  jnz     short loc_180018D19
0x180018cb7  test    dil, 22h
0x180018cbb  jz      loc_180018D59
0x180018cc1  lea     edi, [rax+68h]
0x180018cc4  mov     ecx, edi; cb
0x180018cc6  call    cs:__imp_CoTaskMemAlloc
0x180018ccc  mov     rbx, rax
0x180018ccf  test    rax, rax
0x180018cd2  jz      short loc_180018D32
0x180018cd4  lea     rcx, [rax+8]; void *
0x180018cd8  xor     edx, edx; Val
0x180018cda  lea     r8d, [rbp+60h]; Size
0x180018cde  call    memset_0
0x180018ce3  mov     [rbx], edi
0x180018ce5  lea     rax, ?PageDlgProc@CIncomingConnectionCheckDevsPage@@CAHPEAUHWND__@@I_K_J@Z; CIncomingConnectionCheckDevsPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180018cec  mov     dword ptr [rbx+4], 1000h
0x180018cf3  mov     rcx, cs:hInst
0x180018cfa  mov     [rbx+8], rcx
0x180018cfe  mov     [rbx+28h], rax
0x180018d02  mov     [rbx+30h], rsi
0x180018d06  mov     qword ptr [rbx+10h], 83h
0x180018d0e  mov     qword ptr [rbx+48h], 0BF4h
0x180018d16  mov     [r14], rbx
0x180018d19  xor     ebx, ebx
0x180018d1b  mov     edx, ebp; int
0x180018d1d  mov     rcx, rsi; this
0x180018d20  call    ?UpdateDevicePresenceInPropertyBag@CIncomingConnectionCheckDevsPage@@AEAAXH@Z; CIncomingConnectionCheckDevsPage::UpdateDevicePresenceInPropertyBag(int)
0x180018d25  mov     eax, ebx
0x180018d27  add     rsp, 30h
0x180018d2b  pop     r14
0x180018d2d  pop     rdi
0x180018d2e  pop     rsi
0x180018d2f  pop     rbp
0x180018d30  pop     rbx
0x180018d31  retn
0x180018d32  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180018d38  mov     ebx, 8007000Eh
0x180018d3d  cmp     ecx, 0FFFFFFFFh
0x180018d40  jz      short loc_180018D25
0x180018d42  mov     r9d, ebx
0x180018d45  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x180018d4c  mov     edx, 0Ch; dwFlags
0x180018d51  call    cs:__imp_TracePrintfExA
0x180018d57  jmp     short loc_180018D25
0x180018d59  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180018d5f  mov     ebx, 80004001h
0x180018d64  cmp     ecx, 0FFFFFFFFh
0x180018d67  jz      short loc_180018D25
0x180018d69  mov     [rsp+58h+var_30], ebx
0x180018d6d  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x180018d74  mov     r9d, edi
0x180018d77  mov     [rsp+58h+var_38], edi
0x180018d7b  mov     edx, 0Ch; dwFlags
0x180018d80  call    cs:__imp_TracePrintfExA
0x180018d86  jmp     short loc_180018D25
```
