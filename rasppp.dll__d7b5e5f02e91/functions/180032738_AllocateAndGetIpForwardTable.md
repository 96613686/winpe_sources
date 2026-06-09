# AllocateAndGetIpForwardTable

- ea: `0x180032738`
- end: `0x180032b13`
- name: `AllocateAndGetIpForwardTable`
- size: `987`
- prototype: `__int64 __fastcall(LPVOID *, __int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180032b1c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002dcfc`
- `0x18003230c`
- `0x180032738`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032a1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032a6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032a1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032a6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800328d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032a3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800328d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032a3b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180032852`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180032a82`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180032852`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180032a82`
- `IPHLPAPI!GetIpForwardTable` at `0x180032877`
- `IPHLPAPI!GetIpForwardTable` at `0x180032980`
- `IPHLPAPI!GetIpForwardTable` at `0x180032877`
- `IPHLPAPI!GetIpForwardTable` at `0x180032980`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18003283c`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18003283c`

## string_xrefs

- `0x1800329a5`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x1800329f7`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpForwardTable(LPVOID *a1, __int64 a2, void *a3)
{
  __int64 v5; // rcx
  __int64 result; // rax
  int v7; // esi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  DWORD IpForwardTable; // eax
  DWORD v10; // ebx
  const wchar_t *v11; // rdx
  const CHAR *v12; // rcx
  struct _MIB_IPFORWARDTABLE *v13; // rax
  _DWORD *v14; // rax
  ULONG pdwSize; // [rsp+40h] [rbp-C0h] BYREF
  GUID v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+6Ch] [rbp-94h]
  __int128 v19; // [rsp+7Ch] [rbp-84h]
  int v20; // [rsp+8Ch] [rbp-74h]
  int v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  pdwSize = 0;
  v21 = 0;
  memset(v16, 0, sizeof(v16));
  memset_0(v22, 0, sizeof(v22));
  v5 = qword_18004D658;
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  if ( (_QWORD)xmmword_18004D648 || __PAIR128__(*((unsigned __int64 *)&xmmword_18004D648 + 1), 0) != qword_18004D658 )
  {
    result = NsiGetRoutingDomainIdForCompartment(qword_18004D658, v16);
    if ( (_DWORD)result )
      return result;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v5 )
    {
      LOWORD(v17) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v5,
        L"AllocateAndGetIpForwardTable Begin",
        v16,
        0,
        &v17);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpForwardTable Begin");
  }
  *a1 = 0;
  v7 = 1;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpForwardTable = SetCurrentThreadCompartmentId(1u);
  v10 = IpForwardTable;
  if ( IpForwardTable )
  {
    v7 = 0;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_18004D648 + 1) )
        goto LABEL_26;
      v11 = L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
      goto LABEL_23;
    }
    v12 = "AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_25;
  }
  pdwSize = 0;
  IpForwardTable = GetIpForwardTable(0, &pdwSize, 0);
  v10 = IpForwardTable;
  if ( IpForwardTable != 122 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_18004D648 + 1) )
        goto LABEL_26;
      v11 = L"AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_23:
      LOWORD(v17) = 0;
      LOWORD(v21) = 0;
      FormatRRASErrorString((wchar_t *)&v21, v11, IpForwardTable);
      ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_18004D648 + 1),
        &v21,
        v16,
        0,
        &v17);
      goto LABEL_26;
    }
    v12 = "AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_25:
    TraceHlp(v12);
    goto LABEL_26;
  }
  pdwSize += 280;
  v13 = (struct _MIB_IPFORWARDTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
  *a1 = v13;
  if ( !v13 )
    goto LABEL_15;
  v10 = GetIpForwardTable(v13, &pdwSize, 0);
LABEL_26:
  if ( v10 != 232 )
  {
    if ( !v10 )
      goto LABEL_34;
LABEL_32:
    if ( *a1 )
    {
      HeapFree(a3, 0, *a1);
      *a1 = 0;
    }
    goto LABEL_34;
  }
  if ( *a1 )
  {
    HeapFree(a3, 0, *a1);
    *a1 = 0;
  }
  pdwSize = 68;
  v14 = HeapAlloc(a3, 0x40u, 0x44u);
  *a1 = v14;
  if ( !v14 )
  {
LABEL_15:
    v10 = 14;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v21,
          L"AllocateAndGetIpForwardTable : error %d allocating %d bytes",
          14,
          pdwSize);
        ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_18004D648 + 1),
          &v21,
          v16,
          0,
          &v17);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpForwardTable : error %d allocating %d bytes");
    }
    goto LABEL_32;
  }
  *v14 = 0;
  v10 = 0;
LABEL_34:
  if ( v7 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D658 )
    {
      LOWORD(v17) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D658,
        L"AllocateAndGetIpForwardTable End",
        v16,
        0,
        &v17);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpForwardTable End");
  }
  return v10;
}

```

## disassembly

```asm
0x180032738  mov     [rsp-8+arg_8], rbx
0x18003273d  mov     [rsp-8+arg_18], rsi
0x180032742  push    rbp
0x180032743  push    rdi
0x180032744  push    r12
0x180032746  push    r14
0x180032748  push    r15
0x18003274a  lea     rbp, [rsp-7A0h]
0x180032752  sub     rsp, 8A0h
0x180032759  mov     rax, cs:__security_cookie
0x180032760  xor     rax, rsp
0x180032763  mov     [rbp+7C0h+var_30], rax
0x18003276a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032771  mov     r14, r8
0x180032774  mov     rdi, rcx
0x180032777  xor     r12d, r12d
0x18003277a  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18003277e  xor     edx, edx; Val
0x180032780  mov     [rsp+8C0h+pdwSize], r12d
0x180032785  mov     r8d, 7FCh; Size
0x18003278b  mov     [rbp+7C0h+var_830], r12d
0x18003278f  movdqu  [rsp+8C0h+var_878], xmm0
0x180032795  call    memset_0
0x18003279a  mov     rcx, cs:qword_18004D658
0x1800327a1  xorps   xmm0, xmm0
0x1800327a4  xor     eax, eax
0x1800327a6  mov     [rsp+8C0h+var_858], r12d
0x1800327ab  cmp     qword ptr cs:xmmword_18004D648, r12
0x1800327b2  movups  [rsp+8C0h+var_854], xmm0
0x1800327b7  mov     [rbp+7C0h+var_834], eax
0x1800327ba  movups  [rsp+8C0h+var_844], xmm0
0x1800327bf  movups  [rsp+8C0h+var_868], xmm0
0x1800327c4  jnz     short loc_1800327D4
0x1800327c6  cmp     qword ptr cs:xmmword_18004D648+8, r12
0x1800327cd  jnz     short loc_1800327D4
0x1800327cf  test    rcx, rcx
0x1800327d2  jz      short loc_1800327E6
0x1800327d4  lea     rdx, [rsp+8C0h+var_878]
0x1800327d9  call    NsiGetRoutingDomainIdForCompartment
0x1800327de  test    eax, eax
0x1800327e0  jnz     loc_180032AE7
0x1800327e6  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800327ed  jz      short loc_18003282D
0x1800327ef  test    rcx, rcx
0x1800327f2  jz      short loc_180032839
0x1800327f4  lea     rax, [rsp+8C0h+var_858]
0x1800327f9  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800327ff  mov     [rsp+8C0h+var_898], rax
0x180032804  lea     r9, [rsp+8C0h+var_878]
0x180032809  mov     rax, cs:gIphlpParamTemplateFunc
0x180032810  lea     r8, aAllocateandget_20; "AllocateAndGetIpForwardTable Begin"
0x180032817  mov     rdx, rcx
0x18003281a  mov     [rsp+8C0h+var_8A0], r12
0x18003281f  mov     rcx, cs:gIphlpEtwContext
0x180032826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003282b  jmp     short loc_180032839
0x18003282d  lea     rcx, aAllocateandget_19; "AllocateAndGetIpForwardTable Begin"
0x180032834  call    TraceHlp
0x180032839  mov     [rdi], r12
0x18003283c  call    cs:__imp_GetCurrentThreadCompartmentId
0x180032843  nop     dword ptr [rax+rax+00h]
0x180032848  mov     esi, 1
0x18003284d  mov     r15d, eax
0x180032850  mov     ecx, esi; CompartmentId
0x180032852  call    cs:__imp_SetCurrentThreadCompartmentId
0x180032859  nop     dword ptr [rax+rax+00h]
0x18003285e  mov     ebx, eax
0x180032860  test    eax, eax
0x180032862  jnz     loc_180032990
0x180032868  xor     r8d, r8d; bOrder
0x18003286b  mov     [rsp+8C0h+pdwSize], r12d
0x180032870  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180032875  xor     ecx, ecx; pIpForwardTable
0x180032877  call    cs:__imp_GetIpForwardTable
0x18003287e  nop     dword ptr [rax+rax+00h]
0x180032883  mov     ebx, eax
0x180032885  cmp     eax, 7Ah ; 'z'
0x180032888  jz      short loc_1800328B8
0x18003288a  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180032891  jz      short loc_1800328AC
0x180032893  cmp     qword ptr cs:xmmword_18004D648+8, r12
0x18003289a  jz      loc_180032A05
0x1800328a0  lea     rdx, aAllocateandget_14; "AllocateAndGetIpForwardTable : error %d"...
0x1800328a7  jmp     loc_1800329AC
0x1800328ac  lea     rcx, aAllocateandget_9; "AllocateAndGetIpForwardTable : error %d"...
0x1800328b3  jmp     loc_1800329FE
0x1800328b8  mov     eax, [rsp+8C0h+pdwSize]
0x1800328bc  mov     edx, 40h ; '@'; dwFlags
0x1800328c1  add     eax, 118h
0x1800328c6  mov     rcx, r14; hHeap
0x1800328c9  mov     r8d, eax; dwBytes
0x1800328cc  mov     [rsp+8C0h+pdwSize], eax
0x1800328d0  call    cs:__imp_HeapAlloc
0x1800328d7  nop     dword ptr [rax+rax+00h]
0x1800328dc  mov     [rdi], rax
0x1800328df  test    rax, rax
0x1800328e2  jnz     loc_180032975
0x1800328e8  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800328ef  mov     ebx, 0Eh
0x1800328f4  jz      short loc_18003295D
0x1800328f6  cmp     qword ptr cs:xmmword_18004D648+8, r12
0x1800328fd  jz      loc_180032A5F
0x180032903  mov     r9d, [rsp+8C0h+pdwSize]
0x180032908  lea     rdx, aAllocateandget_3; "AllocateAndGetIpForwardTable : error %d"...
0x18003290f  mov     r8d, ebx
0x180032912  mov     word ptr [rbp+7C0h+var_830], r12w
0x180032917  lea     rcx, [rbp+7C0h+var_830]
0x18003291b  mov     word ptr [rsp+8C0h+var_858], r12w
0x180032921  call    FormatRRASErrorString
0x180032926  mov     rdx, qword ptr cs:xmmword_18004D648+8
0x18003292d  lea     rax, [rsp+8C0h+var_858]
0x180032932  mov     rcx, cs:gIphlpEtwContext
0x180032939  lea     r9, [rsp+8C0h+var_878]
0x18003293e  mov     [rsp+8C0h+var_898], rax
0x180032943  lea     r8, [rbp+7C0h+var_830]
0x180032947  mov     rax, cs:gIphlpParamTemplateFunc
0x18003294e  mov     [rsp+8C0h+var_8A0], r12
0x180032953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032958  jmp     loc_180032A5F
0x18003295d  mov     r8d, [rsp+8C0h+pdwSize]
0x180032962  lea     rcx, aAllocateandget_0; "AllocateAndGetIpForwardTable : error %d"...
0x180032969  mov     edx, ebx
0x18003296b  call    TraceHlp
0x180032970  jmp     loc_180032A5F
0x180032975  xor     r8d, r8d; bOrder
0x180032978  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18003297d  mov     rcx, rax; pIpForwardTable
0x180032980  call    cs:__imp_GetIpForwardTable
0x180032987  nop     dword ptr [rax+rax+00h]
0x18003298c  mov     ebx, eax
0x18003298e  jmp     short loc_180032A05
0x180032990  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180032997  mov     esi, r12d
0x18003299a  jz      short loc_1800329F7
0x18003299c  cmp     qword ptr cs:xmmword_18004D648+8, r12
0x1800329a3  jz      short loc_180032A05
0x1800329a5  lea     rdx, aAllocateandget_1; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x1800329ac  mov     r8d, eax
0x1800329af  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800329b5  lea     rcx, [rbp+7C0h+var_830]
0x1800329b9  mov     word ptr [rbp+7C0h+var_830], r12w
0x1800329be  call    FormatRRASErrorString
0x1800329c3  mov     rdx, qword ptr cs:xmmword_18004D648+8
0x1800329ca  lea     rax, [rsp+8C0h+var_858]
0x1800329cf  mov     rcx, cs:gIphlpEtwContext
0x1800329d6  lea     r9, [rsp+8C0h+var_878]
0x1800329db  mov     [rsp+8C0h+var_898], rax
0x1800329e0  lea     r8, [rbp+7C0h+var_830]
0x1800329e4  mov     rax, cs:gIphlpParamTemplateFunc
0x1800329eb  mov     [rsp+8C0h+var_8A0], r12
0x1800329f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329f5  jmp     short loc_180032A05
0x1800329f7  lea     rcx, aAllocateandget_13; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x1800329fe  mov     edx, eax
0x180032a00  call    TraceHlp
0x180032a05  cmp     ebx, 0E8h
0x180032a0b  jnz     short loc_180032A5B
0x180032a0d  mov     r8, [rdi]; lpMem
0x180032a10  test    r8, r8
0x180032a13  jz      short loc_180032A29
0x180032a15  xor     edx, edx; dwFlags
0x180032a17  mov     rcx, r14; hHeap
0x180032a1a  call    cs:__imp_HeapFree
0x180032a21  nop     dword ptr [rax+rax+00h]
0x180032a26  mov     [rdi], r12
0x180032a29  mov     r8d, 44h ; 'D'; dwBytes
0x180032a2f  mov     rcx, r14; hHeap
0x180032a32  mov     [rsp+8C0h+pdwSize], r8d
0x180032a37  lea     edx, [r8-4]; dwFlags
0x180032a3b  call    cs:__imp_HeapAlloc
0x180032a42  nop     dword ptr [rax+rax+00h]
0x180032a47  mov     [rdi], rax
0x180032a4a  test    rax, rax
0x180032a4d  jz      loc_1800328E8
0x180032a53  mov     [rax], r12d
0x180032a56  mov     ebx, r12d
0x180032a59  jmp     short loc_180032A7B
0x180032a5b  test    ebx, ebx
0x180032a5d  jz      short loc_180032A7B
0x180032a5f  mov     r8, [rdi]; lpMem
0x180032a62  test    r8, r8
0x180032a65  jz      short loc_180032A7B
0x180032a67  xor     edx, edx; dwFlags
0x180032a69  mov     rcx, r14; hHeap
0x180032a6c  call    cs:__imp_HeapFree
0x180032a73  nop     dword ptr [rax+rax+00h]
0x180032a78  mov     [rdi], r12
0x180032a7b  test    esi, esi
0x180032a7d  jz      short loc_180032A8E
0x180032a7f  mov     ecx, r15d; CompartmentId
0x180032a82  call    cs:__imp_SetCurrentThreadCompartmentId
0x180032a89  nop     dword ptr [rax+rax+00h]
0x180032a8e  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180032a95  jz      short loc_180032AD9
0x180032a97  mov     rdx, cs:qword_18004D658
0x180032a9e  test    rdx, rdx
0x180032aa1  jz      short loc_180032AE5
0x180032aa3  mov     rcx, cs:gIphlpEtwContext
0x180032aaa  lea     rax, [rsp+8C0h+var_858]
0x180032aaf  mov     [rsp+8C0h+var_898], rax
0x180032ab4  lea     r9, [rsp+8C0h+var_878]
0x180032ab9  mov     rax, cs:gIphlpParamTemplateFunc
0x180032ac0  lea     r8, aAllocateandget_8; "AllocateAndGetIpForwardTable End"
0x180032ac7  mov     word ptr [rsp+8C0h+var_858], r12w
0x180032acd  mov     [rsp+8C0h+var_8A0], r12
0x180032ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ad7  jmp     short loc_180032AE5
0x180032ad9  lea     rcx, aAllocateandget_2; "AllocateAndGetIpForwardTable End"
0x180032ae0  call    TraceHlp
0x180032ae5  mov     eax, ebx
0x180032ae7  mov     rcx, [rbp+7C0h+var_30]
0x180032aee  xor     rcx, rsp; StackCookie
0x180032af1  call    __security_check_cookie
0x180032af6  lea     r11, [rsp+8C0h+var_20]
0x180032afe  mov     rbx, [r11+38h]
0x180032b02  mov     rsi, [r11+48h]
0x180032b06  mov     rsp, r11
0x180032b09  pop     r15
0x180032b0b  pop     r14
0x180032b0d  pop     r12
0x180032b0f  pop     rdi
0x180032b10  pop     rbp
0x180032b11  retn
```
