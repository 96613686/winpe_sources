# ProcessSaveInterfaceConfigInfo

- ea: `0x18003cce8`
- end: `0x18003cf9f`
- name: `ProcessSaveInterfaceConfigInfo`
- size: `695`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034cd0`
- `0x180034f44`
- `0x18003bfb0`
- `0x18003cfa8`

## callees

- `0x18000ac60`
- `0x180011790`
- `0x18001d7e4`
- `0x18001e94c`
- `0x18003cce8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18003cf0e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003cf1d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003cf0e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003cf1d`
- `ntdll!RtlReleaseResource` at `0x18003ced2`
- `ntdll!RtlReleaseResource` at `0x18003cedf`
- `ntdll!RtlReleaseResource` at `0x18003ced2`
- `ntdll!RtlReleaseResource` at `0x18003cedf`
- `KERNEL32!HeapFree` at `0x18003cf2f`
- `KERNEL32!HeapFree` at `0x18003cf2f`
- `KERNEL32!HeapAlloc` at `0x18003ce55`
- `KERNEL32!HeapAlloc` at `0x18003ce55`

## string_xrefs

- `0x18003cd52`: `ProcessSaveInterfaceConfigInfo`
- `0x18003cf3f`: `ProcessSaveInterfaceConfigInfo: Couldnt find ICB for interface %d`
- `0x18003cdd8`: `ProcessSaveInterfaceConfigInfo: failed to get interface config size. Error %d`
- `0x18003ce80`: `ProcessSaveInterfaceConfigInfo: failed to allocate buffer`

## pseudocode

```c
__int64 __fastcall ProcessSaveInterfaceConfigInfo(unsigned int a1)
{
  char v2; // al
  __int64 i; // rbx
  unsigned int SizeOfInterfaceConfig; // eax
  unsigned int v5; // edi
  __int128 *v6; // r9
  _DWORD *v8; // rax
  void *v9; // rdi
  __int128 *v10; // r9
  SIZE_T dwBytes; // [rsp+30h] [rbp-858h] BYREF
  __int128 v12; // [rsp+38h] [rbp-850h] BYREF
  int v13; // [rsp+48h] [rbp-840h] BYREF
  __int128 v14; // [rsp+4Ch] [rbp-83Ch]
  __int128 v15; // [rsp+5Ch] [rbp-82Ch]
  int v16; // [rsp+6Ch] [rbp-81Ch]
  int v17; // [rsp+70h] [rbp-818h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-814h] BYREF

  LODWORD(dwBytes) = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v13 = 0;
  v16 = 0;
  v2 = Microsoft_Windows_RRASEnableBits;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"Entered: %ws", L"ProcessSaveInterfaceConfigInfo");
    v2 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
      v2 = Microsoft_Windows_RRASEnableBits;
    }
  }
  for ( i = ICBList; (__int64 *)i != &ICBList; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 16) == a1 )
    {
      SizeOfInterfaceConfig = GetSizeOfInterfaceConfig(i, (unsigned int *)&dwBytes);
      v5 = SizeOfInterfaceConfig;
      if ( SizeOfInterfaceConfig )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v17) = 0;
          LOWORD(v13) = 0;
          FormatRRASErrorString(
            &v17,
            L"ProcessSaveInterfaceConfigInfo: failed to get interface config size. Error %d",
            SizeOfInterfaceConfig);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v6 = &v12;
            if ( i != -688 )
              LODWORD(v6) = i + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v17,
              (_DWORD)v6,
              *(_QWORD *)(i + 72),
              (__int64)&v13);
          }
        }
        return v5;
      }
      else
      {
        v8 = HeapAlloc(IPRouterHeap, 8u, (unsigned int)dwBytes);
        v9 = v8;
        if ( v8 )
        {
          GetInterfaceConfiguration(i, v8, dwBytes);
          RtlReleaseResource(&stru_18008C4A0);
          RtlReleaseResource(&Resource);
          ((void (__fastcall *)(_QWORD, __int64, void *, _QWORD))SaveInterfaceInfo)(
            *(_QWORD *)(i + 184),
            33,
            v9,
            (unsigned int)dwBytes);
          RtlAcquireResourceExclusive(&Resource, 1u);
          RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
          HeapFree(IPRouterHeap, 0, v9);
          return 0;
        }
        else
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v13) = 0;
            v10 = &v12;
            if ( i != -688 )
              LODWORD(v10) = i + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)L"ProcessSaveInterfaceConfigInfo: failed to allocate buffer",
              (_DWORD)v10,
              *(_QWORD *)(i + 72),
              (__int64)&v13);
          }
          return 8;
        }
      }
    }
  }
  if ( v2 < 0 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"ProcessSaveInterfaceConfigInfo: Couldnt find ICB for interface %d", a1);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
  }
  return 87;
}

```

## disassembly

```asm
0x18003cce8  mov     [rsp+arg_8], rbx
0x18003cced  push    rdi
0x18003ccee  sub     rsp, 880h
0x18003ccf5  mov     rax, cs:__security_cookie
0x18003ccfc  xor     rax, rsp
0x18003ccff  mov     [rsp+888h+var_18], rax
0x18003cd07  mov     edi, ecx
0x18003cd09  mov     dword ptr [rsp+888h+dwBytes], 0
0x18003cd11  xor     eax, eax
0x18003cd13  lea     rcx, [rsp+888h+var_814]; void *
0x18003cd18  xor     edx, edx; Val
0x18003cd1a  mov     [rsp+888h+var_818], eax
0x18003cd1e  mov     r8d, 7FCh; Size
0x18003cd24  call    memset_0
0x18003cd29  xor     eax, eax
0x18003cd2b  xorps   xmm0, xmm0
0x18003cd2e  mov     [rsp+888h+var_840], eax
0x18003cd32  mov     [rsp+888h+var_81C], eax
0x18003cd36  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003cd3d  movups  [rsp+888h+var_83C], xmm0
0x18003cd42  movups  [rsp+888h+var_82C], xmm0
0x18003cd47  movups  [rsp+888h+var_850], xmm0
0x18003cd4c  test    al, al
0x18003cd4e  jns     short loc_18003CD99
0x18003cd50  xor     eax, eax
0x18003cd52  lea     r8, aProcesssaveint_0; "ProcessSaveInterfaceConfigInfo"
0x18003cd59  lea     rdx, aEnteredWs; "Entered: %ws"
0x18003cd60  mov     word ptr [rsp+888h+var_818], ax
0x18003cd65  lea     rcx, [rsp+888h+var_818]
0x18003cd6a  call    FormatRRASErrorString
0x18003cd6f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003cd76  test    al, al
0x18003cd78  jns     short loc_18003CD99
0x18003cd7a  lea     r8, [rsp+888h+var_818]
0x18003cd7f  lea     rdx, RasRtrmgrTraceInfo
0x18003cd86  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003cd8d  call    McTemplateU0z_EventWriteTransfer
0x18003cd92  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003cd99  mov     rbx, cs:ICBList
0x18003cda0  lea     rcx, ICBList
0x18003cda7  cmp     rbx, rcx
0x18003cdaa  jz      loc_18003CF39
0x18003cdb0  cmp     [rbx+10h], edi
0x18003cdb3  jz      short loc_18003CDBA
0x18003cdb5  mov     rbx, [rbx]
0x18003cdb8  jmp     short loc_18003CDA0
0x18003cdba  lea     rdx, [rsp+888h+dwBytes]
0x18003cdbf  mov     rcx, rbx
0x18003cdc2  call    GetSizeOfInterfaceConfig
0x18003cdc7  mov     edi, eax
0x18003cdc9  test    eax, eax
0x18003cdcb  jz      short loc_18003CE44
0x18003cdcd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cdd4  jz      short loc_18003CE3D
0x18003cdd6  xor     ecx, ecx
0x18003cdd8  lea     rdx, aProcesssaveint; "ProcessSaveInterfaceConfigInfo: failed "...
0x18003cddf  mov     word ptr [rsp+888h+var_818], cx
0x18003cde4  mov     r8d, eax
0x18003cde7  mov     word ptr [rsp+888h+var_840], cx
0x18003cdec  lea     rcx, [rsp+888h+var_818]
0x18003cdf1  call    FormatRRASErrorString
0x18003cdf6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cdfd  jz      short loc_18003CE3D
0x18003cdff  lea     rax, [rbx+2B0h]
0x18003ce06  test    rax, rax
0x18003ce09  lea     r9, [rsp+888h+var_850]
0x18003ce0e  lea     r8, [rsp+888h+var_818]
0x18003ce13  cmovnz  r9, rax
0x18003ce17  lea     rdx, RasRtrMgrParamTraceError
0x18003ce1e  lea     rax, [rsp+888h+var_840]
0x18003ce23  mov     [rsp+888h+var_860], rax
0x18003ce28  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ce2f  mov     rax, [rbx+48h]
0x18003ce33  mov     [rsp+888h+var_868], rax
0x18003ce38  call    McTemplateU0zjzz_EventWriteTransfer
0x18003ce3d  mov     eax, edi
0x18003ce3f  jmp     loc_18003CF7E
0x18003ce44  mov     r8d, dword ptr [rsp+888h+dwBytes]; dwBytes
0x18003ce49  mov     edx, 8; dwFlags
0x18003ce4e  mov     rcx, cs:IPRouterHeap; hHeap
0x18003ce55  call    cs:__imp_HeapAlloc
0x18003ce5b  mov     rdi, rax
0x18003ce5e  test    rax, rax
0x18003ce61  jnz     short loc_18003CEBB
0x18003ce63  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003ce6a  jz      short loc_18003CEB1
0x18003ce6c  lea     rcx, [rbx+2B0h]
0x18003ce73  mov     word ptr [rsp+888h+var_840], ax
0x18003ce78  test    rcx, rcx
0x18003ce7b  lea     r9, [rsp+888h+var_850]
0x18003ce80  lea     r8, aProcesssaveint_1; "ProcessSaveInterfaceConfigInfo: failed "...
0x18003ce87  cmovnz  r9, rcx
0x18003ce8b  lea     rdx, RasRtrmgrParamTraceInfo
0x18003ce92  lea     rcx, [rsp+888h+var_840]
0x18003ce97  mov     [rsp+888h+var_860], rcx
0x18003ce9c  mov     rcx, [rbx+48h]
0x18003cea0  mov     [rsp+888h+var_868], rcx
0x18003cea5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ceac  call    McTemplateU0zjzz_EventWriteTransfer
0x18003ceb1  mov     eax, 8
0x18003ceb6  jmp     loc_18003CF7E
0x18003cebb  mov     r8d, dword ptr [rsp+888h+dwBytes]
0x18003cec0  mov     rdx, rdi
0x18003cec3  mov     rcx, rbx
0x18003cec6  call    GetInterfaceConfiguration
0x18003cecb  lea     rcx, stru_18008C4A0; Resource
0x18003ced2  call    cs:__imp_RtlReleaseResource
0x18003ced8  lea     rcx, Resource; Resource
0x18003cedf  call    cs:__imp_RtlReleaseResource
0x18003cee5  mov     r9d, dword ptr [rsp+888h+dwBytes]
0x18003ceea  mov     r8, rdi
0x18003ceed  mov     rcx, [rbx+0B8h]
0x18003cef4  mov     edx, 21h ; '!'
0x18003cef9  mov     rax, cs:SaveInterfaceInfo
0x18003cf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf05  mov     dl, 1; Wait
0x18003cf07  lea     rcx, Resource; Resource
0x18003cf0e  call    cs:__imp_RtlAcquireResourceExclusive
0x18003cf14  mov     dl, 1; Wait
0x18003cf16  lea     rcx, stru_18008C4A0; Resource
0x18003cf1d  call    cs:__imp_RtlAcquireResourceExclusive
0x18003cf23  mov     rcx, cs:IPRouterHeap; hHeap
0x18003cf2a  mov     r8, rdi; lpMem
0x18003cf2d  xor     edx, edx; dwFlags
0x18003cf2f  call    cs:__imp_HeapFree
0x18003cf35  xor     eax, eax
0x18003cf37  jmp     short loc_18003CF7E
0x18003cf39  test    al, al
0x18003cf3b  jns     short loc_18003CF79
0x18003cf3d  xor     eax, eax
0x18003cf3f  lea     rdx, aProcesssaveint_2; "ProcessSaveInterfaceConfigInfo: Couldnt"...
0x18003cf46  mov     r8d, edi
0x18003cf49  mov     word ptr [rsp+888h+var_818], ax
0x18003cf4e  lea     rcx, [rsp+888h+var_818]
0x18003cf53  call    FormatRRASErrorString
0x18003cf58  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003cf5f  jge     short loc_18003CF79
0x18003cf61  lea     r8, [rsp+888h+var_818]
0x18003cf66  lea     rdx, RasRtrmgrTraceInfo
0x18003cf6d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003cf74  call    McTemplateU0z_EventWriteTransfer
0x18003cf79  mov     eax, 57h ; 'W'
0x18003cf7e  mov     rcx, [rsp+888h+var_18]
0x18003cf86  xor     rcx, rsp; StackCookie
0x18003cf89  call    __security_check_cookie
0x18003cf8e  mov     rbx, [rsp+888h+arg_8]
0x18003cf96  add     rsp, 880h
0x18003cf9d  pop     rdi
0x18003cf9e  retn
```
