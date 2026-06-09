# SvrImpl_NcaNetworkOpen(void *,void *,_GUID const *,void * *)

- ea: `0x18000833c`
- end: `0x180008557`
- name: `?SvrImpl_NcaNetworkOpen@@YAKPEAX0PEBU_GUID@@PEAPEAX@Z`
- size: `539`
- prototype: `__int64 __fastcall(void *, void *, struct _GUID *, struct NCA_INTSERVER_ENGINE_HANDLE_ ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b810`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x180007088`
- `0x18000833c`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000849c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000849c`
- `RPCRT4!UuidEqual` at `0x1800083fa`
- `RPCRT4!UuidEqual` at `0x1800083fa`

## string_xrefs

- `0x18000839f`: `NcaNetworkOpen`
- `0x180008534`: `NcaNetworkOpen`

## pseudocode

```c
__int64 __fastcall SvrImpl_NcaNetworkOpen(
        void *a1,
        void *a2,
        struct _GUID *a3,
        struct NCA_INTSERVER_ENGINE_HANDLE_ ***a4)
{
  PVOID *v7; // rcx
  unsigned int IsEngineValid; // ebx
  struct NCA_INTSERVER_ENGINE_HANDLE_ **v9; // rdi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  struct NCA_INTSERVER_ENGINE_HANDLE_ ***v13; // rax
  RPC_STATUS Status; // [rsp+60h] [rbp+8h] BYREF
  int v16; // [rsp+64h] [rbp+Ch]

  v16 = HIDWORD(a1);
  Status = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v7, ApiActivityStart, L"NcaNetworkOpen");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*a4 )
  {
    if ( UuidEqual(a3, (UUID *)&NCA_NETWORK_DIRECTACCESS, &Status) )
    {
      v12 = NcaAlloc(32);
      v9 = (struct NCA_INTSERVER_ENGINE_HANDLE_ **)v12;
      if ( v12 )
      {
        *(_QWORD *)v12 = 0;
        *(_QWORD *)(v12 + 8) = 0;
        *(_QWORD *)(v12 + 24) = a2;
        *(_DWORD *)(v12 + 16) = 0;
        *(_DWORD *)(v12 + 20) = 1;
        EnterCriticalSection(&gNcaApiSrvImpl);
        IsEngineValid = NcaApiSrvImplIsEngineValid(v9[3]);
        if ( !IsEngineValid )
        {
          v13 = (struct NCA_INTSERVER_ENGINE_HANDLE_ ***)qword_180028C98;
          if ( *(__int64 **)qword_180028C98 != &qword_180028C90 )
            __fastfail(3u);
          *v9 = (struct NCA_INTSERVER_ENGINE_HANDLE_ *)&qword_180028C90;
          v9[1] = (struct NCA_INTSERVER_ENGINE_HANDLE_ *)v13;
          *v13 = v9;
          qword_180028C98 = (__int64)v9;
          *a4 = v9;
        }
        LeaveCriticalSection(&gNcaApiSrvImpl);
        if ( !IsEngineValid )
          goto LABEL_25;
        goto LABEL_24;
      }
      IsEngineValid = 14;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_24:
        NcaFree(v9);
        goto LABEL_25;
      }
      v11 = 38;
    }
    else
    {
      v9 = 0;
      IsEngineValid = 87;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v11 = 37;
    }
    WPP_SF_d(v10[2], v11, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, IsEngineValid);
    goto LABEL_24;
  }
  IsEngineValid = 0;
  if ( v7 == &WPP_GLOBAL_Control )
    goto LABEL_29;
  if ( (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    WPP_SF_d(v7[2], 36, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, 0);
LABEL_25:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_d(v7[2], 39, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, IsEngineValid);
LABEL_29:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v7, ApiActivityEnd, L"NcaNetworkOpen", IsEngineValid);
  return IsEngineValid;
}

```

## disassembly

```asm
0x18000833c  mov     qword ptr [rsp+Status], rcx
0x180008341  push    rbx
0x180008342  push    rbp
0x180008343  push    rsi
0x180008344  push    rdi
0x180008345  push    r12
0x180008347  push    r13
0x180008349  sub     rsp, 28h
0x18000834d  mov     rsi, r9
0x180008350  mov     [rsp+58h+Status], 0
0x180008358  mov     rbx, r8
0x18000835b  mov     rbp, rdx
0x18000835e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008365  lea     r12, WPP_GLOBAL_Control
0x18000836c  lea     r13, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180008373  cmp     rcx, r12
0x180008376  jz      short loc_180008396
0x180008378  test    byte ptr [rcx+1Ch], 8
0x18000837c  jz      short loc_180008396
0x18000837e  mov     rcx, [rcx+10h]
0x180008382  mov     edx, 23h ; '#'
0x180008387  mov     r8, r13
0x18000838a  call    WPP_SF_
0x18000838f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008396  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000839d  jz      short loc_1800083B9
0x18000839f  lea     r8, aNcanetworkopen; "NcaNetworkOpen"
0x1800083a6  lea     rdx, ApiActivityStart
0x1800083ad  call    McTemplateU0z_EventWriteTransfer
0x1800083b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083b9  cmp     qword ptr [rsi], 0
0x1800083bd  jz      short loc_1800083EB
0x1800083bf  xor     ebx, ebx
0x1800083c1  cmp     rcx, r12
0x1800083c4  jz      loc_180008528
0x1800083ca  test    byte ptr [rcx+1Ch], 1
0x1800083ce  jz      loc_180008509
0x1800083d4  mov     rcx, [rcx+10h]
0x1800083d8  lea     edx, [rbx+24h]
0x1800083db  xor     r9d, r9d
0x1800083de  mov     r8, r13
0x1800083e1  call    WPP_SF_d
0x1800083e6  jmp     loc_180008502
0x1800083eb  lea     r8, [rsp+58h+Status]; Status
0x1800083f0  mov     rcx, rbx; Uuid1
0x1800083f3  lea     rdx, NCA_NETWORK_DIRECTACCESS; Uuid2
0x1800083fa  call    cs:__imp_UuidEqual
0x180008401  nop     dword ptr [rax+rax+00h]
0x180008406  test    eax, eax
0x180008408  jnz     short loc_180008440
0x18000840a  xor     edi, edi
0x18000840c  lea     ebx, [rax+57h]
0x18000840f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008416  cmp     rcx, r12
0x180008419  jz      loc_1800084FA
0x18000841f  test    byte ptr [rcx+1Ch], 1
0x180008423  jz      loc_1800084FA
0x180008429  lea     edx, [rax+25h]
0x18000842c  mov     rcx, [rcx+10h]
0x180008430  mov     r9d, ebx
0x180008433  mov     r8, r13
0x180008436  call    WPP_SF_d
0x18000843b  jmp     loc_1800084FA
0x180008440  mov     ecx, 20h ; ' '
0x180008445  call    NcaAlloc
0x18000844a  mov     rdi, rax
0x18000844d  test    rax, rax
0x180008450  jnz     short loc_180008474
0x180008452  lea     ebx, [rax+0Eh]
0x180008455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000845c  cmp     rcx, r12
0x18000845f  jz      loc_1800084FA
0x180008465  test    byte ptr [rcx+1Ch], 1
0x180008469  jz      loc_1800084FA
0x18000846f  lea     edx, [rax+26h]
0x180008472  jmp     short loc_18000842C
0x180008474  mov     qword ptr [rax], 0
0x18000847b  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x180008482  mov     qword ptr [rax+8], 0
0x18000848a  mov     [rax+18h], rbp
0x18000848e  mov     dword ptr [rax+10h], 0
0x180008495  mov     dword ptr [rax+14h], 1
0x18000849c  call    cs:__imp_EnterCriticalSection
0x1800084a3  nop     dword ptr [rax+rax+00h]
0x1800084a8  mov     rcx, [rdi+18h]; struct NCA_INTSERVER_ENGINE_HANDLE_ *
0x1800084ac  call    ?NcaApiSrvImplIsEngineValid@@YAKPEAUNCA_INTSERVER_ENGINE_HANDLE_@@@Z; NcaApiSrvImplIsEngineValid(NCA_INTSERVER_ENGINE_HANDLE_ *)
0x1800084b1  mov     ebx, eax
0x1800084b3  test    eax, eax
0x1800084b5  jnz     short loc_1800084E3
0x1800084b7  mov     rax, cs:qword_180028C98
0x1800084be  lea     rcx, qword_180028C90
0x1800084c5  cmp     [rax], rcx
0x1800084c8  jz      short loc_1800084CF
0x1800084ca  lea     ecx, [rbx+3]
0x1800084cd  int     29h; Win8: RtlFailFast(ecx)
0x1800084cf  mov     [rdi], rcx
0x1800084d2  mov     [rdi+8], rax
0x1800084d6  mov     [rax], rdi
0x1800084d9  mov     cs:qword_180028C98, rdi
0x1800084e0  mov     [rsi], rdi
0x1800084e3  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x1800084ea  call    cs:__imp_LeaveCriticalSection
0x1800084f1  nop     dword ptr [rax+rax+00h]
0x1800084f6  test    ebx, ebx
0x1800084f8  jz      short loc_180008502
0x1800084fa  mov     rcx, rdi; lpMem
0x1800084fd  call    NcaFree
0x180008502  mov     rcx, cs:WPP_GLOBAL_Control
0x180008509  cmp     rcx, r12
0x18000850c  jz      short loc_180008528
0x18000850e  test    byte ptr [rcx+1Ch], 8
0x180008512  jz      short loc_180008528
0x180008514  mov     rcx, [rcx+10h]
0x180008518  mov     edx, 27h ; '''
0x18000851d  mov     r9d, ebx
0x180008520  mov     r8, r13
0x180008523  call    WPP_SF_d
0x180008528  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000852f  jz      short loc_180008547
0x180008531  mov     r9d, ebx
0x180008534  lea     r8, aNcanetworkopen; "NcaNetworkOpen"
0x18000853b  lea     rdx, ApiActivityEnd
0x180008542  call    McTemplateU0zx_EventWriteTransfer
0x180008547  mov     eax, ebx
0x180008549  add     rsp, 28h
0x18000854d  pop     r13
0x18000854f  pop     r12
0x180008551  pop     rdi
0x180008552  pop     rsi
0x180008553  pop     rbp
0x180008554  pop     rbx
0x180008555  retn
```
