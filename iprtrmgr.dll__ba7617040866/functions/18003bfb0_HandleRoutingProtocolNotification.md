# HandleRoutingProtocolNotification

- ea: `0x18003bfb0`
- end: `0x18003c1a3`
- name: `HandleRoutingProtocolNotification`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180050e40`

## callees

- `0x18000ac60`
- `0x18003bfb0`
- `0x18003cac0`
- `0x18003cce8`
- `0x18003cfa8`
- `0x18003d344`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18003c05b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003c06a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003c05b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003c06a`
- `ntdll!RtlReleaseResource` at `0x18003c160`
- `ntdll!RtlReleaseResource` at `0x18003c16d`
- `ntdll!RtlReleaseResource` at `0x18003c160`
- `ntdll!RtlReleaseResource` at `0x18003c16d`
- `KERNEL32!FreeLibrary` at `0x18003c116`
- `KERNEL32!FreeLibrary` at `0x18003c116`
- `KERNEL32!Sleep` at `0x18003c10c`
- `KERNEL32!Sleep` at `0x18003c10c`
- `KERNEL32!HeapFree` at `0x18003c141`
- `KERNEL32!HeapFree` at `0x18003c141`

## string_xrefs

- `0x18003c014`: `HandleRoutingProtocolNotification`

## pseudocode

```c
__int64 __fastcall HandleRoutingProtocolNotification(unsigned int a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // r14
  __int64 *v4; // rdi
  __int64 v5; // rcx
  __int64 **v6; // rax
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+28h] [rbp-D8h] BYREF
  int v10; // [rsp+30h] [rbp-D0h]
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  char v12[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entered: %ws", L"HandleRoutingProtocolNotification");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v11);
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
  v2 = (__int64 *)g_leProtoCbListV6;
  v3 = (__int64 *)&g_leProtoCbListV4;
  if ( a1 )
    v2 = (__int64 *)g_leProtoCbListV4;
  else
    v3 = &g_leProtoCbListV6;
  if ( v2 != v3 )
  {
    do
    {
      while ( !((unsigned int (__fastcall *)(int *, __int64 *))v2[21])(&v8, &v9) )
      {
        if ( v8 )
        {
          switch ( v8 )
          {
            case 1:
              ProcessSaveGlobalConfigInfo(a1);
              break;
            case 2:
              ProcessSaveInterfaceConfigInfo(v9);
              break;
            case 3:
              ProcessUpdateComplete((__int64)v2, (unsigned int *)&v9);
              break;
          }
        }
        else
        {
          *((_DWORD *)v2 + 4) = 2;
        }
      }
      v4 = (__int64 *)*v2;
      if ( *((_DWORD *)v2 + 4) == 2 )
      {
        RemoveProtocolFromAllInterfaces((__int64)v2);
        Sleep(0);
        FreeLibrary((HMODULE)v2[5]);
        v5 = *v2;
        if ( *(__int64 **)(*v2 + 8) != v2 || (v6 = (__int64 **)v2[1], *v6 != v2) )
          __fastfail(3u);
        *v6 = (__int64 *)v5;
        *(_QWORD *)(v5 + 8) = v6;
        HeapFree(IPRouterHeap, 0, v2);
        --TotalRoutingProtocols;
      }
      v2 = v4;
    }
    while ( v4 != v3 );
  }
  RtlReleaseResource(&stru_18008C4A0);
  RtlReleaseResource(&Resource);
  return 0;
}

```

## disassembly

```asm
0x18003bfb0  mov     [rsp-8+arg_8], rbx
0x18003bfb5  mov     [rsp-8+arg_10], rsi
0x18003bfba  push    rbp
0x18003bfbb  push    rdi
0x18003bfbc  push    r14
0x18003bfbe  lea     rbp, [rsp-750h]
0x18003bfc6  sub     rsp, 850h
0x18003bfcd  mov     rax, cs:__security_cookie
0x18003bfd4  xor     rax, rsp
0x18003bfd7  mov     [rbp+760h+var_20], rax
0x18003bfde  xor     eax, eax
0x18003bfe0  mov     [rsp+860h+var_840], 0
0x18003bfe8  mov     esi, ecx
0x18003bfea  mov     [rsp+860h+var_838], rax
0x18003bfef  lea     rcx, [rsp+860h+var_81C]; void *
0x18003bff4  mov     [rsp+860h+var_830], eax
0x18003bff8  xor     edx, edx; Val
0x18003bffa  mov     [rsp+860h+var_820], eax
0x18003bffe  mov     r8d, 7FCh; Size
0x18003c004  call    memset_0
0x18003c009  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003c010  jge     short loc_18003C052
0x18003c012  xor     eax, eax
0x18003c014  lea     r8, aHandleroutingp; "HandleRoutingProtocolNotification"
0x18003c01b  lea     rdx, aEnteredWs; "Entered: %ws"
0x18003c022  mov     word ptr [rsp+860h+var_820], ax
0x18003c027  lea     rcx, [rsp+860h+var_820]
0x18003c02c  call    FormatRRASErrorString
0x18003c031  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003c038  jge     short loc_18003C052
0x18003c03a  lea     r8, [rsp+860h+var_820]
0x18003c03f  lea     rdx, RasRtrmgrTraceInfo
0x18003c046  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c04d  call    McTemplateU0z_EventWriteTransfer
0x18003c052  mov     dl, 1; Wait
0x18003c054  lea     rcx, Resource; Resource
0x18003c05b  call    cs:__imp_RtlAcquireResourceExclusive
0x18003c061  mov     dl, 1; Wait
0x18003c063  lea     rcx, stru_18008C4A0; Resource
0x18003c06a  call    cs:__imp_RtlAcquireResourceExclusive
0x18003c070  mov     rbx, cs:g_leProtoCbListV6
0x18003c077  lea     rax, g_leProtoCbListV6
0x18003c07e  test    esi, esi
0x18003c080  lea     r14, g_leProtoCbListV4
0x18003c087  cmovnz  rbx, cs:g_leProtoCbListV4
0x18003c08f  cmovz   r14, rax
0x18003c093  cmp     rbx, r14
0x18003c096  jz      loc_18003C159
0x18003c09c  mov     rax, [rbx+0A8h]
0x18003c0a3  lea     rdx, [rsp+860h+var_838]
0x18003c0a8  lea     rcx, [rsp+860h+var_840]
0x18003c0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0b2  test    eax, eax
0x18003c0b4  jnz     short loc_18003C0F9
0x18003c0b6  mov     ecx, [rsp+860h+var_840]
0x18003c0ba  test    ecx, ecx
0x18003c0bc  jz      short loc_18003C0F0
0x18003c0be  sub     ecx, 1
0x18003c0c1  jz      short loc_18003C0E7
0x18003c0c3  sub     ecx, 1
0x18003c0c6  jz      short loc_18003C0DC
0x18003c0c8  cmp     ecx, 1
0x18003c0cb  jnz     short loc_18003C09C
0x18003c0cd  lea     rdx, [rsp+860h+var_838]
0x18003c0d2  mov     rcx, rbx
0x18003c0d5  call    ProcessUpdateComplete
0x18003c0da  jmp     short loc_18003C09C
0x18003c0dc  mov     ecx, dword ptr [rsp+860h+var_838]
0x18003c0e0  call    ProcessSaveInterfaceConfigInfo
0x18003c0e5  jmp     short loc_18003C09C
0x18003c0e7  mov     ecx, esi
0x18003c0e9  call    ProcessSaveGlobalConfigInfo
0x18003c0ee  jmp     short loc_18003C09C
0x18003c0f0  mov     dword ptr [rbx+10h], 2
0x18003c0f7  jmp     short loc_18003C09C
0x18003c0f9  cmp     dword ptr [rbx+10h], 2
0x18003c0fd  mov     rdi, [rbx]
0x18003c100  jnz     short loc_18003C14D
0x18003c102  mov     rcx, rbx
0x18003c105  call    RemoveProtocolFromAllInterfaces
0x18003c10a  xor     ecx, ecx; dwMilliseconds
0x18003c10c  call    cs:__imp_Sleep
0x18003c112  mov     rcx, [rbx+28h]; hLibModule
0x18003c116  call    cs:__imp_FreeLibrary
0x18003c11c  mov     rcx, [rbx]
0x18003c11f  cmp     [rcx+8], rbx
0x18003c123  jnz     short loc_18003C19C
0x18003c125  mov     rax, [rbx+8]
0x18003c129  cmp     [rax], rbx
0x18003c12c  jnz     short loc_18003C19C
0x18003c12e  mov     [rax], rcx
0x18003c131  mov     r8, rbx; lpMem
0x18003c134  mov     [rcx+8], rax
0x18003c138  xor     edx, edx; dwFlags
0x18003c13a  mov     rcx, cs:IPRouterHeap; hHeap
0x18003c141  call    cs:__imp_HeapFree
0x18003c147  dec     cs:TotalRoutingProtocols
0x18003c14d  mov     rbx, rdi
0x18003c150  cmp     rdi, r14
0x18003c153  jnz     loc_18003C09C
0x18003c159  lea     rcx, stru_18008C4A0; Resource
0x18003c160  call    cs:__imp_RtlReleaseResource
0x18003c166  lea     rcx, Resource; Resource
0x18003c16d  call    cs:__imp_RtlReleaseResource
0x18003c173  xor     eax, eax
0x18003c175  mov     rcx, [rbp+760h+var_20]
0x18003c17c  xor     rcx, rsp; StackCookie
0x18003c17f  call    __security_check_cookie
0x18003c184  lea     r11, [rsp+860h+var_10]
0x18003c18c  mov     rbx, [r11+28h]
0x18003c190  mov     rsi, [r11+30h]
0x18003c194  mov     rsp, r11
0x18003c197  pop     r14
0x18003c199  pop     rdi
0x18003c19a  pop     rbp
0x18003c19b  retn
0x18003c19c  mov     ecx, 3
0x18003c1a1  int     29h; Win8: RtlFailFast(ecx)
```
