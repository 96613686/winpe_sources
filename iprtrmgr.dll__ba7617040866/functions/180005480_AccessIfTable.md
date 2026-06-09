# AccessIfTable

- ea: `0x180005480`
- end: `0x1800056ee`
- name: `AccessIfTable`
- size: `622`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180005480`
- `0x18000ac60`
- `0x180017bb8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000569f`
- `ntdll!RtlReleaseResource` at `0x18000569f`
- `ntdll!RtlAcquireResourceShared` at `0x180005568`
- `ntdll!RtlAcquireResourceShared` at `0x180005568`

## string_xrefs

- `0x1800054f3`: `AccessIfTable`
- `0x18000553f`: `Leaving: AccessIfTable`
- `0x1800056b5`: `Leaving: AccessIfTable`
- `0x180005581`: `AccessIfTable: No valid entries found`
- `0x180005654`: `AccessIfTable: Error %d getting statistics for %ws`

## pseudocode

```c
__int64 __fastcall AccessIfTable(int a1, __int64 a2, __int64 a3, _DWORD *a4, _DWORD *a5, _DWORD *a6, int a7)
{
  char v9; // al
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // edx
  int v14; // edi
  __int64 i; // rbx
  int v16; // eax
  unsigned int InterfaceStatistics; // eax
  int v18; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v19[2044]; // [rsp+34h] [rbp-844h] BYREF

  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Entered: %ws", L"AccessIfTable");
    v9 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v18);
      v9 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a1 == 1 )
  {
    RtlAcquireResourceShared(&Resource, 1u);
    if ( g_ulNumNonClientInterfaces )
    {
      v12 = 860LL * (unsigned int)g_ulNumNonClientInterfaces;
      v13 = v12 + 20;
      if ( (unsigned int)*a4 >= (unsigned __int64)(v12 + 20) )
      {
        *a5 = 1;
        *a4 = v13;
        v14 = 0;
        for ( i = ICBList; (__int64 *)i != &ICBList; i = *(_QWORD *)i )
        {
          v16 = *(_DWORD *)(i + 144);
          if ( v16 && (v16 != 4 || *(_DWORD *)(i + 512)) && *(_DWORD *)(i + 516) == (a7 == 33) )
          {
            InterfaceStatistics = GetInterfaceStatistics(i, &a5[215 * v14 + 3]);
            if ( InterfaceStatistics )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v18) = 0;
                FormatRRASErrorString(
                  &v18,
                  L"AccessIfTable: Error %d getting statistics for %ws",
                  InterfaceStatistics,
                  *(_QWORD *)(i + 72));
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v18);
              }
            }
            else
            {
              ++v14;
            }
          }
        }
        a5[2] = v14;
        v11 = 0;
      }
      else
      {
        *a4 = v13;
        v11 = 122;
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"AccessIfTable: No valid entries found");
      if ( *a4 >= 0x368u )
      {
        a5[2] = 0;
        v11 = 0;
        *a5 = 1;
      }
      else
      {
        v11 = 122;
      }
      *a4 = 872;
    }
    RtlReleaseResource(&Resource);
    *a6 = 1;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIfTable");
    return v11;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIfTable");
    return 87;
  }
}

```

## disassembly

```asm
0x180005480  push    rbx
0x180005482  push    rsi
0x180005483  push    rdi
0x180005484  push    r13
0x180005486  push    r14
0x180005488  push    r15
0x18000548a  sub     rsp, 848h
0x180005491  mov     rax, cs:__security_cookie
0x180005498  xor     rax, rsp
0x18000549b  mov     [rsp+878h+var_48], rax
0x1800054a3  mov     rsi, [rsp+878h+arg_20]
0x1800054ab  xor     r14d, r14d
0x1800054ae  cmp     [rsp+878h+arg_30], 21h ; '!'
0x1800054b6  mov     ebx, ecx
0x1800054b8  mov     r15, [rsp+878h+arg_28]
0x1800054c0  lea     rcx, [rsp+878h+var_844]; void *
0x1800054c5  setz    r14b
0x1800054c9  mov     r8d, 7FCh; Size
0x1800054cf  xor     eax, eax
0x1800054d1  xor     edx, edx; Val
0x1800054d3  mov     [rsp+878h+var_848], eax
0x1800054d7  mov     rdi, r9
0x1800054da  call    memset_0
0x1800054df  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800054e6  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800054ed  test    al, al
0x1800054ef  jns     short loc_180005536
0x1800054f1  xor     eax, eax
0x1800054f3  lea     r8, aAccessiftable; "AccessIfTable"
0x1800054fa  lea     rdx, aEnteredWs; "Entered: %ws"
0x180005501  mov     word ptr [rsp+878h+var_848], ax
0x180005506  lea     rcx, [rsp+878h+var_848]
0x18000550b  call    FormatRRASErrorString
0x180005510  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005517  test    al, al
0x180005519  jns     short loc_180005536
0x18000551b  lea     r8, [rsp+878h+var_848]
0x180005520  mov     rcx, r13
0x180005523  lea     rdx, RasRtrmgrTraceInfo
0x18000552a  call    McTemplateU0z_EventWriteTransfer
0x18000552f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005536  cmp     ebx, 1
0x180005539  jz      short loc_18000555F
0x18000553b  test    al, 80h
0x18000553d  jz      short loc_180005555
0x18000553f  lea     r8, aLeavingAccessi_13; "Leaving: AccessIfTable"
0x180005546  mov     rcx, r13
0x180005549  lea     rdx, RasRtrmgrTraceInfo
0x180005550  call    McTemplateU0z_EventWriteTransfer
0x180005555  mov     eax, 57h ; 'W'
0x18000555a  jmp     loc_1800056CD
0x18000555f  mov     dl, 1; Wait
0x180005561  lea     rcx, Resource; Resource
0x180005568  call    cs:__imp_RtlAcquireResourceShared
0x18000556e  mov     ecx, cs:g_ulNumNonClientInterfaces
0x180005574  test    ecx, ecx
0x180005576  jnz     short loc_1800055BD
0x180005578  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000557f  jz      short loc_180005597
0x180005581  lea     r8, aAccessiftableN; "AccessIfTable: No valid entries found"
0x180005588  mov     rcx, r13
0x18000558b  lea     rdx, RasRtrmgrTraceInfo
0x180005592  call    McTemplateU0z_EventWriteTransfer
0x180005597  mov     eax, 368h
0x18000559c  cmp     [rdi], eax
0x18000559e  jnb     short loc_1800055A7
0x1800055a0  mov     ebx, 7Ah ; 'z'
0x1800055a5  jmp     short loc_1800055B6
0x1800055a7  mov     dword ptr [rsi+8], 0
0x1800055ae  xor     ebx, ebx
0x1800055b0  mov     dword ptr [rsi], 1
0x1800055b6  mov     [rdi], eax
0x1800055b8  jmp     loc_180005698
0x1800055bd  mov     eax, [rdi]
0x1800055bf  imul    edx, ecx, 35Ch
0x1800055c5  imul    rcx, 35Ch
0x1800055cc  add     edx, 14h
0x1800055cf  add     rcx, 14h
0x1800055d3  cmp     rax, rcx
0x1800055d6  jnb     short loc_1800055E4
0x1800055d8  mov     [rdi], edx
0x1800055da  mov     ebx, 7Ah ; 'z'
0x1800055df  jmp     loc_180005698
0x1800055e4  mov     dword ptr [rsi], 1
0x1800055ea  mov     [rdi], edx
0x1800055ec  xor     edi, edi
0x1800055ee  mov     rbx, cs:ICBList
0x1800055f5  lea     rax, ICBList
0x1800055fc  cmp     rbx, rax
0x1800055ff  jz      loc_180005693
0x180005605  mov     eax, [rbx+90h]
0x18000560b  test    eax, eax
0x18000560d  jz      short loc_18000568B
0x18000560f  cmp     eax, 4
0x180005612  jnz     short loc_18000561D
0x180005614  cmp     dword ptr [rbx+200h], 0
0x18000561b  jz      short loc_18000568B
0x18000561d  cmp     [rbx+204h], r14d
0x180005624  jnz     short loc_18000568B
0x180005626  mov     eax, edi
0x180005628  mov     rcx, rbx
0x18000562b  imul    rdx, rax, 35Ch
0x180005632  add     rdx, 0Ch
0x180005636  add     rdx, rsi
0x180005639  call    GetInterfaceStatistics
0x18000563e  mov     r8d, eax
0x180005641  test    eax, eax
0x180005643  jnz     short loc_180005649
0x180005645  inc     edi
0x180005647  jmp     short loc_18000568B
0x180005649  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180005650  jz      short loc_18000568B
0x180005652  xor     eax, eax
0x180005654  lea     rdx, aAccessiftableE; "AccessIfTable: Error %d getting statist"...
0x18000565b  mov     word ptr [rsp+878h+var_848], ax
0x180005660  lea     rcx, [rsp+878h+var_848]
0x180005665  mov     r9, [rbx+48h]
0x180005669  call    FormatRRASErrorString
0x18000566e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180005675  jz      short loc_18000568B
0x180005677  lea     r8, [rsp+878h+var_848]
0x18000567c  mov     rcx, r13
0x18000567f  lea     rdx, RasRtrMgrTraceError
0x180005686  call    McTemplateU0z_EventWriteTransfer
0x18000568b  mov     rbx, [rbx]
0x18000568e  jmp     loc_1800055F5
0x180005693  mov     [rsi+8], edi
0x180005696  xor     ebx, ebx
0x180005698  lea     rcx, Resource; Resource
0x18000569f  call    cs:__imp_RtlReleaseResource
0x1800056a5  mov     dword ptr [r15], 1
0x1800056ac  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800056b3  jz      short loc_1800056CB
0x1800056b5  lea     r8, aLeavingAccessi_13; "Leaving: AccessIfTable"
0x1800056bc  mov     rcx, r13
0x1800056bf  lea     rdx, RasRtrmgrTraceInfo
0x1800056c6  call    McTemplateU0z_EventWriteTransfer
0x1800056cb  mov     eax, ebx
0x1800056cd  mov     rcx, [rsp+878h+var_48]
0x1800056d5  xor     rcx, rsp; StackCookie
0x1800056d8  call    __security_check_cookie
0x1800056dd  add     rsp, 848h
0x1800056e4  pop     r15
0x1800056e6  pop     r14
0x1800056e8  pop     r13
0x1800056ea  pop     rdi
0x1800056eb  pop     rsi
0x1800056ec  pop     rbx
0x1800056ed  retn
```
