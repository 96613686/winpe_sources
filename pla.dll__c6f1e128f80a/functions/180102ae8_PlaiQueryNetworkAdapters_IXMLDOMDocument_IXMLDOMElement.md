# PlaiQueryNetworkAdapters(IXMLDOMDocument *,IXMLDOMElement *)

- ea: `0x180102ae8`
- end: `0x1801032cf`
- name: `?PlaiQueryNetworkAdapters@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@@Z`
- size: `2023`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180135d78`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18001b4fc`
- `0x18001cbe0`
- `0x18002b3a0`
- `0x18005e3a8`
- `0x180097a78`
- `0x1800b6a74`
- `0x180102ae8`
- `0x18013ae9a`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x180102b4d`
- `WS2_32!__imp_WSAStartup` at `0x180102b4d`
- `WS2_32!__imp_WSACleanup` at `0x18010329d`
- `WS2_32!__imp_WSACleanup` at `0x18010329d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180102c9d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180102c9d`

## pseudocode

```c
__int64 __fastcall PlaiQueryNetworkAdapters(struct IXMLDOMDocument *a1, struct IXMLDOMElement *a2)
{
  IP_ADAPTER_ADDRESSES_LH *v4; // r12
  struct IXMLDOMElement *v5; // r14
  struct IXMLDOMElement *v6; // rdi
  unsigned int v7; // eax
  int v8; // eax
  int IpAddresses; // ebx
  __int64 v10; // rax
  ULONG AdaptersAddresses; // eax
  const unsigned __int16 *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rax
  struct _IP_ADAPTER_ADDRESSES_LH *i; // rsi
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  int SizePointer; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+78h] [rbp-88h] BYREF
  ULONG v26; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMElement *v27; // [rsp+88h] [rbp-78h] BYREF
  struct IXMLDOMElement *v28; // [rsp+90h] [rbp-70h] BYREF
  WSAData WSAData; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v30[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v31[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v32[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v33[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v34[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v35[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v36[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v37[64]; // [rsp+5C0h] [rbp+4C0h] BYREF

  v4 = 0;
  v26 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v28 = 0;
  v27 = 0;
  v5 = 0;
  v6 = 0;
  v7 = WSAStartup(0x202u, &WSAData);
  v8 = PlaiHResultFromWin32(v7);
  IpAddresses = v8;
  if ( v8 >= 0 )
  {
    v26 = 1024;
    do
    {
      if ( v4 )
        PlaiFree(v4, 1);
      v4 = (IP_ADAPTER_ADDRESSES_LH *)PlaiAlloc(v26, 1, 0, qword_180147320, SizePointer);
      if ( !v4 )
      {
        IpAddresses = -2147024882;
        v24 = -2147024882;
        v25 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v37, 0x4000000000000800uLL);
          v21 = -1;
          do
            ++v21;
          while ( v37[v21] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v24,
            4,
            qword_180147320,
            1,
            &v25,
            4,
            "PlaiQueryNetworkAdapters",
            25);
        }
        goto LABEL_72;
      }
      AdaptersAddresses = GetAdaptersAddresses(0, 8u, 0, v4, &v26);
      IpAddresses = PlaiHResultFromWin32(AdaptersAddresses);
    }
    while ( IpAddresses == -2147024785 );
    if ( IpAddresses >= 0 )
    {
      IpAddresses = PlaiCreateReportTable(a1, a2, L"networkInformation", v12, L"info", &v28, 0);
      if ( IpAddresses >= 0 )
      {
        v5 = v28;
        for ( i = v4; i; i = i->Next )
        {
          if ( v6 )
          {
            ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
            LODWORD(v6) = 0;
            v27 = 0;
          }
          v16 = PlaiAddItemToReport(a1, v5, &v27);
          IpAddresses = v16;
          if ( v16 < 0 )
          {
            v25 = (int)v6;
            v24 = v16;
            if ( (_DWORD)xmmword_180169738 != (_DWORD)v6
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v36, 0x4000000000000800uLL);
              v20 = -1;
              do
                ++v20;
              while ( v36[v20] != (_WORD)v6 );
              EventingWriteEvent(
                &g_Eventing,
                PLA_EVENT_ERROR,
                5,
                &v24,
                4,
                qword_180147320,
                1,
                &v25,
                4,
                "PlaiQueryNetworkAdapters",
                25);
            }
            v6 = v27;
            break;
          }
          v6 = v27;
          IpAddresses = PlaiAddDataToReportItem(a1, v27, L"networkInformationNicName", i->FriendlyName);
          if ( IpAddresses < 0 )
          {
            v25 = 0;
            v24 = IpAddresses;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v35, 0x4000000000000800uLL);
              v19 = -1;
              do
                ++v19;
              while ( v35[v19] );
              goto LABEL_19;
            }
            break;
          }
          IpAddresses = PlaiGetIpAddresses(a1, v6, i);
          if ( IpAddresses < 0 )
          {
            v25 = 0;
            v24 = IpAddresses;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v34, 0x4000000000000800uLL);
              v18 = -1;
              do
                ++v18;
              while ( v34[v18] );
              goto LABEL_19;
            }
            break;
          }
          IpAddresses = PlaiGetOffloadInfo(a1, v6, i);
          if ( IpAddresses < 0 )
          {
            v25 = 0;
            v24 = IpAddresses;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v33, 0x4000000000000800uLL);
              v17 = -1;
              do
                ++v17;
              while ( v33[v17] );
              goto LABEL_19;
            }
            break;
          }
        }
      }
      else
      {
        v25 = 0;
        v24 = IpAddresses;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v32, 0x4000000000000800uLL);
          v14 = -1;
          do
            ++v14;
          while ( v32[v14] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v24,
            4,
            qword_180147320,
            1,
            &v25,
            4,
            "PlaiQueryNetworkAdapters",
            25);
        }
        v5 = v28;
      }
    }
    else
    {
      v25 = 0;
      v24 = IpAddresses;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v31, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v31[v13] );
LABEL_19:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v24,
          4,
          qword_180147320,
          1,
          &v25,
          4,
          "PlaiQueryNetworkAdapters",
          25);
      }
    }
    PlaiFree(v4, 1);
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
    if ( v5 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
LABEL_72:
    WSACleanup();
  }
  else
  {
    v24 = 0;
    v25 = v8;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v30, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v30[v10] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v25,
        4,
        qword_180147320,
        1,
        &v24,
        4,
        "PlaiQueryNetworkAdapters",
        25);
    }
  }
  return (unsigned int)IpAddresses;
}

```

## disassembly

```asm
0x180102ae8  mov     [rsp-8+arg_10], rbx
0x180102aed  push    rbp
0x180102aee  push    rsi
0x180102aef  push    rdi
0x180102af0  push    r12
0x180102af2  push    r13
0x180102af4  push    r14
0x180102af6  push    r15
0x180102af8  lea     rbp, [rsp-550h]
0x180102b00  sub     rsp, 650h
0x180102b07  mov     rax, cs:__security_cookie
0x180102b0e  xor     rax, rsp
0x180102b11  mov     [rbp+580h+var_40], rax
0x180102b18  mov     rsi, rdx
0x180102b1b  mov     r15, rcx
0x180102b1e  xor     r12d, r12d
0x180102b21  lea     rcx, [rbp+580h+WSAData]; void *
0x180102b25  xor     edx, edx; Val
0x180102b27  mov     [rbp+580h+var_600], r12d
0x180102b2b  mov     r8d, 198h; Size
0x180102b31  call    memset_0
0x180102b36  mov     ecx, 202h; wVersionRequested
0x180102b3b  mov     [rbp+580h+var_5F0], r12
0x180102b3f  lea     rdx, [rbp+580h+WSAData]; lpWSAData
0x180102b43  mov     [rbp+580h+var_5F8], r12
0x180102b47  mov     r14d, r12d
0x180102b4a  mov     edi, r12d
0x180102b4d  call    cs:__imp_WSAStartup
0x180102b53  mov     ecx, eax; unsigned int
0x180102b55  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180102b5a  mov     ebx, eax
0x180102b5c  test    eax, eax
0x180102b5e  jns     loc_180102C45
0x180102b64  cmp     dword ptr cs:xmmword_180169738, r12d
0x180102b6b  mov     [rsp+680h+var_610], r12d
0x180102b70  mov     [rsp+680h+var_608], eax
0x180102b74  jz      loc_1801032A3
0x180102b7a  mov     rdx, 4000000000000800h; unsigned __int64
0x180102b84  test    qword ptr cs:xmmword_180169738+8, rdx
0x180102b8b  jz      loc_1801032A3
0x180102b91  mov     rax, cs:qword_180169748
0x180102b98  and     rax, rdx
0x180102b9b  cmp     cs:qword_180169748, rax
0x180102ba2  jnz     loc_1801032A3
0x180102ba8  lea     rcx, [rbp+580h+var_440]; unsigned __int16 *
0x180102baf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180102bb4  lea     rcx, [rbp+580h+var_440]
0x180102bbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180102bbf  inc     rax
0x180102bc2  cmp     [rcx+rax*2], r12w
0x180102bc7  jnz     short loc_180102BBF
0x180102bc9  lea     ecx, [rax+rax]
0x180102bcc  add     rcx, 2
0x180102bd0  lea     rax, [rbp+580h+var_440]
0x180102bd7  mov     [rsp+680h+var_620], rcx
0x180102bdc  lea     r9, [rsp+680h+var_608]
0x180102be1  mov     [rsp+680h+var_628], rax
0x180102be6  lea     rcx, [rsp+680h+var_610]
0x180102beb  mov     [rsp+680h+var_630], 19h
0x180102bf4  lea     rax, aPlaiquerynetwo; "PlaiQueryNetworkAdapters"
0x180102bfb  mov     [rsp+680h+var_638], rax
0x180102c00  lea     rdx, PLA_EVENT_ERROR
0x180102c07  mov     eax, 4
0x180102c0c  mov     [rsp+680h+var_640], rax
0x180102c11  mov     [rsp+680h+var_648], rcx
0x180102c16  lea     rcx, qword_180147320
0x180102c1d  lea     r13d, [rax-3]
0x180102c21  mov     [rsp+680h+var_650], r13
0x180102c26  lea     r8d, [rax+1]
0x180102c2a  mov     [rsp+680h+var_658], rcx
0x180102c2f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180102c36  mov     [rsp+680h+SizePointer], rax
0x180102c3b  call    EventingWriteEvent
0x180102c40  jmp     loc_1801032A3
0x180102c45  mov     [rbp+580h+var_600], 400h
0x180102c4c  mov     r13d, 1
0x180102c52  lea     rbx, qword_180147320
0x180102c59  test    r12, r12
0x180102c5c  jz      short loc_180102C69
0x180102c5e  mov     edx, r13d; int
0x180102c61  mov     rcx, r12; lpMem
0x180102c64  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x180102c69  mov     ecx, [rbp+580h+var_600]; dwBytes
0x180102c6c  mov     r9, rbx; char *
0x180102c6f  xor     r8d, r8d; int
0x180102c72  mov     edx, r13d; int
0x180102c75  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180102c7a  mov     r12, rax
0x180102c7d  xor     eax, eax
0x180102c7f  test    r12, r12
0x180102c82  jz      loc_1801031C1
0x180102c88  xor     r8d, r8d; Reserved
0x180102c8b  lea     rax, [rbp+580h+var_600]
0x180102c8f  mov     r9, r12; AdapterAddresses
0x180102c92  mov     [rsp+680h+SizePointer], rax; SizePointer
0x180102c97  xor     ecx, ecx; Family
0x180102c99  lea     edx, [r8+8]; Flags
0x180102c9d  call    cs:__imp_GetAdaptersAddresses
0x180102ca3  mov     ecx, eax; unsigned int
0x180102ca5  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180102caa  mov     ebx, eax
0x180102cac  cmp     eax, 8007006Fh
0x180102cb1  jz      short loc_180102C52
0x180102cb3  xor     eax, eax
0x180102cb5  test    ebx, ebx
0x180102cb7  jns     loc_180102D99
0x180102cbd  cmp     dword ptr cs:xmmword_180169738, eax
0x180102cc3  mov     [rsp+680h+var_608], eax
0x180102cc7  mov     [rsp+680h+var_610], ebx
0x180102ccb  jz      loc_180103185
0x180102cd1  mov     rdx, 4000000000000800h; unsigned __int64
0x180102cdb  test    qword ptr cs:xmmword_180169738+8, rdx
0x180102ce2  jz      loc_180103185
0x180102ce8  mov     rax, cs:qword_180169748
0x180102cef  and     rax, rdx
0x180102cf2  cmp     cs:qword_180169748, rax
0x180102cf9  jnz     loc_180103185
0x180102cff  lea     rcx, [rbp+580h+var_3C0]; unsigned __int16 *
0x180102d06  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180102d0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180102d0f  lea     rdx, [rbp+580h+var_3C0]
0x180102d16  xor     ecx, ecx
0x180102d18  inc     rax
0x180102d1b  cmp     [rdx+rax*2], cx
0x180102d1f  jnz     short loc_180102D18
0x180102d21  lea     ecx, [rax+rax]
0x180102d24  lea     rax, [rbp+580h+var_3C0]
0x180102d2b  add     rcx, 2
0x180102d2f  lea     r9, [rsp+680h+var_610]
0x180102d34  mov     [rsp+680h+var_620], rcx
0x180102d39  lea     rdx, PLA_EVENT_ERROR
0x180102d40  mov     [rsp+680h+var_628], rax
0x180102d45  lea     rcx, [rsp+680h+var_608]
0x180102d4a  mov     [rsp+680h+var_630], 19h
0x180102d53  lea     rax, aPlaiquerynetwo; "PlaiQueryNetworkAdapters"
0x180102d5a  mov     [rsp+680h+var_638], rax
0x180102d5f  mov     eax, 4
0x180102d64  mov     [rsp+680h+var_640], rax
0x180102d69  mov     [rsp+680h+var_648], rcx
0x180102d6e  lea     rcx, qword_180147320
0x180102d75  mov     [rsp+680h+var_650], r13
0x180102d7a  mov     [rsp+680h+var_658], rcx
0x180102d7f  lea     r8d, [rax+1]
0x180102d83  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180102d8a  mov     [rsp+680h+SizePointer], rax
0x180102d8f  call    EventingWriteEvent
0x180102d94  jmp     loc_180103185
0x180102d99  mov     [rsp+680h+var_650], rax; struct IXMLDOMElement **
0x180102d9e  lea     r8, aNetworkinforma; "networkInformation"
0x180102da5  lea     rax, [rbp+580h+var_5F0]
0x180102da9  mov     rdx, rsi; struct IXMLDOMElement *
0x180102dac  mov     [rsp+680h+var_658], rax; struct IXMLDOMElement **
0x180102db1  mov     rcx, r15; struct IXMLDOMDocument *
0x180102db4  lea     rax, aInfo; "info"
0x180102dbb  mov     [rsp+680h+SizePointer], rax; unsigned __int16 *
0x180102dc0  call    ?PlaiCreateReportTable@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG22PEAPEAU2@3@Z; PlaiCreateReportTable(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *,IXMLDOMElement * *)
0x180102dc5  mov     ebx, eax
0x180102dc7  xor     eax, eax
0x180102dc9  test    ebx, ebx
0x180102dcb  jns     loc_180102EB1
0x180102dd1  cmp     dword ptr cs:xmmword_180169738, eax
0x180102dd7  mov     [rsp+680h+var_608], eax
0x180102ddb  mov     [rsp+680h+var_610], ebx
0x180102ddf  jz      loc_180102EA8
0x180102de5  mov     rdx, 4000000000000800h; unsigned __int64
0x180102def  test    qword ptr cs:xmmword_180169738+8, rdx
0x180102df6  jz      loc_180102EA8
0x180102dfc  mov     rax, cs:qword_180169748
0x180102e03  and     rax, rdx
0x180102e06  cmp     cs:qword_180169748, rax
0x180102e0d  jnz     loc_180102EA8
0x180102e13  lea     rcx, [rbp+580h+var_340]; unsigned __int16 *
0x180102e1a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180102e1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180102e23  lea     rdx, [rbp+580h+var_340]
0x180102e2a  xor     ecx, ecx
0x180102e2c  inc     rax
0x180102e2f  cmp     [rdx+rax*2], cx
0x180102e33  jnz     short loc_180102E2C
0x180102e35  lea     ecx, [rax+rax]
0x180102e38  add     rcx, 2
0x180102e3c  lea     rax, [rbp+580h+var_340]
0x180102e43  mov     [rsp+680h+var_620], rcx
0x180102e48  lea     r9, [rsp+680h+var_610]
0x180102e4d  mov     [rsp+680h+var_628], rax
0x180102e52  lea     rcx, [rsp+680h+var_608]
0x180102e57  mov     [rsp+680h+var_630], 19h
0x180102e60  lea     rax, aPlaiquerynetwo; "PlaiQueryNetworkAdapters"
0x180102e67  mov     [rsp+680h+var_638], rax
0x180102e6c  lea     rdx, PLA_EVENT_ERROR
0x180102e73  mov     eax, 4
0x180102e78  mov     [rsp+680h+var_640], rax
0x180102e7d  mov     [rsp+680h+var_648], rcx
0x180102e82  lea     rcx, qword_180147320
0x180102e89  mov     [rsp+680h+var_650], r13
0x180102e8e  mov     [rsp+680h+var_658], rcx
0x180102e93  lea     r8d, [rax+1]
0x180102e97  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180102e9e  mov     [rsp+680h+SizePointer], rax
0x180102ea3  call    EventingWriteEvent
0x180102ea8  mov     r14, [rbp+580h+var_5F0]
0x180102eac  jmp     loc_180103185
0x180102eb1  mov     r14, [rbp+580h+var_5F0]
0x180102eb5  mov     rsi, r12
0x180102eb8  test    rsi, rsi
0x180102ebb  jz      loc_180103185
0x180102ec1  test    rdi, rdi
0x180102ec4  jz      short loc_180102EDB
0x180102ec6  mov     rax, [rdi]
0x180102ec9  mov     rcx, rdi
0x180102ecc  mov     rax, [rax+10h]
0x180102ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102ed5  xor     edi, edi
0x180102ed7  mov     [rbp+580h+var_5F8], rdi
0x180102edb  lea     r8, [rbp+580h+var_5F8]; struct IXMLDOMElement **
0x180102edf  mov     rdx, r14; struct IXMLDOMElement *
0x180102ee2  mov     rcx, r15; struct IXMLDOMDocument *
0x180102ee5  call    ?PlaiAddItemToReport@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAPEAU2@@Z; PlaiAddItemToReport(IXMLDOMDocument *,IXMLDOMElement *,IXMLDOMElement * *)
0x180102eea  mov     ebx, eax
0x180102eec  test    eax, eax
0x180102eee  js      loc_1801030AC
0x180102ef4  mov     rdi, [rbp+580h+var_5F8]
0x180102ef8  lea     r8, aNetworkinforma_0; "networkInformationNicName"
0x180102eff  mov     r9, [rsi+48h]; unsigned __int16 *
0x180102f03  mov     rdx, rdi; struct IXMLDOMElement *
0x180102f06  mov     rcx, r15; struct IXMLDOMDocument *
0x180102f09  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x180102f0e  mov     ebx, eax
0x180102f10  xor     eax, eax
0x180102f12  test    ebx, ebx
0x180102f14  js      loc_180103039
0x180102f1a  mov     r8, rsi; struct _IP_ADAPTER_ADDRESSES_LH *
0x180102f1d  mov     rdx, rdi; struct IXMLDOMElement *
0x180102f20  mov     rcx, r15; struct IXMLDOMDocument *
0x180102f23  call    ?PlaiGetIpAddresses@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; PlaiGetIpAddresses(IXMLDOMDocument *,IXMLDOMElement *,_IP_ADAPTER_ADDRESSES_LH *)
0x180102f28  mov     ebx, eax
0x180102f2a  xor     eax, eax
0x180102f2c  test    ebx, ebx
0x180102f2e  js      loc_180102FC6
0x180102f34  mov     r8, rsi; struct _IP_ADAPTER_ADDRESSES_LH *
0x180102f37  mov     rdx, rdi; struct IXMLDOMElement *
0x180102f3a  mov     rcx, r15; struct IXMLDOMDocument *
0x180102f3d  call    ?PlaiGetOffloadInfo@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; PlaiGetOffloadInfo(IXMLDOMDocument *,IXMLDOMElement *,_IP_ADAPTER_ADDRESSES_LH *)
0x180102f42  mov     ebx, eax
0x180102f44  xor     eax, eax
0x180102f46  test    ebx, ebx
0x180102f48  js      short loc_180102F53
0x180102f4a  mov     rsi, [rsi+8]
0x180102f4e  jmp     loc_180102EB8
0x180102f53  cmp     dword ptr cs:xmmword_180169738, eax
0x180102f59  mov     [rsp+680h+var_608], eax
0x180102f5d  mov     [rsp+680h+var_610], ebx
0x180102f61  jz      loc_180103185
0x180102f67  mov     rdx, 4000000000000800h; unsigned __int64
0x180102f71  test    qword ptr cs:xmmword_180169738+8, rdx
0x180102f78  jz      loc_180103185
0x180102f7e  mov     rax, cs:qword_180169748
0x180102f85  and     rax, rdx
0x180102f88  cmp     cs:qword_180169748, rax
0x180102f8f  jnz     loc_180103185
0x180102f95  lea     rcx, [rbp+580h+var_2C0]; unsigned __int16 *
0x180102f9c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180102fa1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180102fa5  lea     rdx, [rbp+580h+var_2C0]
0x180102fac  xor     ecx, ecx
0x180102fae  inc     rax
0x180102fb1  cmp     [rdx+rax*2], cx
0x180102fb5  jnz     short loc_180102FAE
0x180102fb7  lea     ecx, [rax+rax]
0x180102fba  lea     rax, [rbp+580h+var_2C0]
0x180102fc1  jmp     loc_180102D2B
0x180102fc6  cmp     dword ptr cs:xmmword_180169738, eax
0x180102fcc  mov     [rsp+680h+var_608], eax
0x180102fd0  mov     [rsp+680h+var_610], ebx
0x180102fd4  jz      loc_180103185
0x180102fda  mov     rdx, 4000000000000800h; unsigned __int64
0x180102fe4  test    qword ptr cs:xmmword_180169738+8, rdx
0x180102feb  jz      loc_180103185
0x180102ff1  mov     rax, cs:qword_180169748
0x180102ff8  and     rax, rdx
0x180102ffb  cmp     cs:qword_180169748, rax
0x180103002  jnz     loc_180103185
0x180103008  lea     rcx, [rbp+580h+var_240]; unsigned __int16 *
0x18010300f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180103014  or      rax, 0FFFFFFFFFFFFFFFFh
0x180103018  lea     rdx, [rbp+580h+var_240]
0x18010301f  xor     ecx, ecx
0x180103021  inc     rax
0x180103024  cmp     [rdx+rax*2], cx
0x180103028  jnz     short loc_180103021
0x18010302a  lea     ecx, [rax+rax]
0x18010302d  lea     rax, [rbp+580h+var_240]
0x180103034  jmp     loc_180102D2B
0x180103039  cmp     dword ptr cs:xmmword_180169738, eax
0x18010303f  mov     [rsp+680h+var_608], eax
0x180103043  mov     [rsp+680h+var_610], ebx
0x180103047  jz      loc_180103185
0x18010304d  mov     rdx, 4000000000000800h; unsigned __int64
0x180103057  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010305e  jz      loc_180103185
  ... truncated ...
```
