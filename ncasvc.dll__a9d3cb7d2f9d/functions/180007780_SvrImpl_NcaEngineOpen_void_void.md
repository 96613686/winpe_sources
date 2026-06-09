# SvrImpl_NcaEngineOpen(void *,void * *)

- ea: `0x180007780`
- end: `0x18000794d`
- name: `?SvrImpl_NcaEngineOpen@@YAKPEAXPEAPEAX@Z`
- size: `461`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b3b0`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x180007780`
- `0x180017708`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077f6`

## string_xrefs

- `0x1800077dc`: `NcaEngineOpen`
- `0x180007923`: `NcaEngineOpen`

## pseudocode

```c
__int64 __fastcall SvrImpl_NcaEngineOpen(void *a1, void **a2)
{
  PVOID v4; // rcx
  _QWORD *v5; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // eax
  _QWORD *v11; // rax
  PVOID v12; // rcx
  struct NCA_USER_ *v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v4, ApiActivityStart, L"NcaEngineOpen");
  EnterCriticalSection(&gNcaApiSrvImpl);
  if ( *a2 )
  {
    v5 = 0;
    v6 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 26;
      v9 = 0;
LABEL_10:
      WPP_SF_d(v7[2], v8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v9);
    }
  }
  else
  {
    v5 = (_QWORD *)NcaAlloc(24);
    if ( v5 )
    {
      v10 = NcaUserStoreCreate(a1, &v14);
      v6 = v10;
      if ( v10 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 28;
          v9 = v10;
          goto LABEL_10;
        }
      }
      else
      {
        v5[2] = v14;
        v11 = (_QWORD *)qword_180028C88;
        if ( *(__int64 **)qword_180028C88 != &qword_180028C80 )
          __fastfail(3u);
        *v5 = &qword_180028C80;
        v5[1] = v11;
        *v11 = v5;
        qword_180028C88 = (__int64)v5;
        *a2 = v5;
      }
    }
    else
    {
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 27;
        v9 = 14;
        goto LABEL_10;
      }
    }
  }
  LeaveCriticalSection(&gNcaApiSrvImpl);
  if ( v6 )
    NcaFree(v5);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v6);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v12, ApiActivityEnd, L"NcaEngineOpen", v6);
  return v6;
}

```

## disassembly

```asm
0x180007780  mov     [rsp+arg_0], rbx
0x180007785  mov     [rsp+arg_10], rsi
0x18000778a  push    rdi
0x18000778b  push    r14
0x18000778d  push    r15
0x18000778f  sub     rsp, 20h
0x180007793  mov     rsi, rdx
0x180007796  mov     [rsp+38h+arg_8], 0
0x18000779f  mov     rbx, rcx
0x1800077a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a9  lea     r14, WPP_GLOBAL_Control
0x1800077b0  lea     r15, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x1800077b7  cmp     rcx, r14
0x1800077ba  jz      short loc_1800077D3
0x1800077bc  test    byte ptr [rcx+1Ch], 8
0x1800077c0  jz      short loc_1800077D3
0x1800077c2  mov     rcx, [rcx+10h]
0x1800077c6  mov     edx, 19h
0x1800077cb  mov     r8, r15
0x1800077ce  call    WPP_SF_
0x1800077d3  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800077da  jz      short loc_1800077EF
0x1800077dc  lea     r8, aNcaengineopen; "NcaEngineOpen"
0x1800077e3  lea     rdx, ApiActivityStart
0x1800077ea  call    McTemplateU0z_EventWriteTransfer
0x1800077ef  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x1800077f6  call    cs:__imp_EnterCriticalSection
0x1800077fd  nop     dword ptr [rax+rax+00h]
0x180007802  cmp     qword ptr [rsi], 0
0x180007806  jz      short loc_18000783D
0x180007808  xor     edi, edi
0x18000780a  xor     ebx, ebx
0x18000780c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007813  cmp     rcx, r14
0x180007816  jz      loc_1800078D2
0x18000781c  test    byte ptr [rcx+1Ch], 1
0x180007820  jz      loc_1800078D2
0x180007826  lea     edx, [rdi+1Ah]
0x180007829  xor     r9d, r9d
0x18000782c  mov     rcx, [rcx+10h]
0x180007830  mov     r8, r15
0x180007833  call    WPP_SF_d
0x180007838  jmp     loc_1800078D2
0x18000783d  mov     ecx, 18h
0x180007842  call    NcaAlloc
0x180007847  mov     rdi, rax
0x18000784a  test    rax, rax
0x18000784d  jnz     short loc_18000786C
0x18000784f  lea     ebx, [rax+0Eh]
0x180007852  mov     rcx, cs:WPP_GLOBAL_Control
0x180007859  cmp     rcx, r14
0x18000785c  jz      short loc_1800078D2
0x18000785e  test    byte ptr [rcx+1Ch], 1
0x180007862  jz      short loc_1800078D2
0x180007864  lea     edx, [rax+1Bh]
0x180007867  mov     r9d, ebx
0x18000786a  jmp     short loc_18000782C
0x18000786c  lea     rdx, [rsp+38h+arg_8]; struct NCA_USER_ **
0x180007871  mov     rcx, rbx; void *
0x180007874  call    ?NcaUserStoreCreate@@YAKPEAXPEAPEAUNCA_USER_@@@Z; NcaUserStoreCreate(void *,NCA_USER_ * *)
0x180007879  mov     ebx, eax
0x18000787b  test    eax, eax
0x18000787d  jz      short loc_18000789B
0x18000787f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007886  cmp     rcx, r14
0x180007889  jz      short loc_1800078D2
0x18000788b  test    byte ptr [rcx+1Ch], 1
0x18000788f  jz      short loc_1800078D2
0x180007891  mov     edx, 1Ch
0x180007896  mov     r9d, eax
0x180007899  jmp     short loc_18000782C
0x18000789b  mov     rax, [rsp+38h+arg_8]
0x1800078a0  lea     rcx, qword_180028C80
0x1800078a7  mov     [rdi+10h], rax
0x1800078ab  mov     rax, cs:qword_180028C88
0x1800078b2  cmp     [rax], rcx
0x1800078b5  jz      short loc_1800078BE
0x1800078b7  mov     ecx, 3
0x1800078bc  int     29h; Win8: RtlFailFast(ecx)
0x1800078be  mov     [rdi], rcx
0x1800078c1  mov     [rdi+8], rax
0x1800078c5  mov     [rax], rdi
0x1800078c8  mov     cs:qword_180028C88, rdi
0x1800078cf  mov     [rsi], rdi
0x1800078d2  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x1800078d9  call    cs:__imp_LeaveCriticalSection
0x1800078e0  nop     dword ptr [rax+rax+00h]
0x1800078e5  test    ebx, ebx
0x1800078e7  jz      short loc_1800078F1
0x1800078e9  mov     rcx, rdi; lpMem
0x1800078ec  call    NcaFree
0x1800078f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078f8  cmp     rcx, r14
0x1800078fb  jz      short loc_180007917
0x1800078fd  test    byte ptr [rcx+1Ch], 8
0x180007901  jz      short loc_180007917
0x180007903  mov     rcx, [rcx+10h]
0x180007907  mov     edx, 1Dh
0x18000790c  mov     r9d, ebx
0x18000790f  mov     r8, r15
0x180007912  call    WPP_SF_d
0x180007917  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000791e  jz      short loc_180007936
0x180007920  mov     r9d, ebx
0x180007923  lea     r8, aNcaengineopen; "NcaEngineOpen"
0x18000792a  lea     rdx, ApiActivityEnd
0x180007931  call    McTemplateU0zx_EventWriteTransfer
0x180007936  mov     rsi, [rsp+38h+arg_10]
0x18000793b  mov     eax, ebx
0x18000793d  mov     rbx, [rsp+38h+arg_0]
0x180007942  add     rsp, 20h
0x180007946  pop     r15
0x180007948  pop     r14
0x18000794a  pop     rdi
0x18000794b  retn
```
