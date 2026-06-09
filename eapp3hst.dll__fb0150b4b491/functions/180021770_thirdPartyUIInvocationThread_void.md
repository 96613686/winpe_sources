# thirdPartyUIInvocationThread(void *)

- ea: `0x180021770`
- end: `0x180021b20`
- name: `?thirdPartyUIInvocationThread@@YAIPEAX@Z`
- size: `944`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x180006c0c`
- `0x18000d0e8`
- `0x18000d184`
- `0x1800126f8`
- `0x180016400`
- `0x18001b154`
- `0x1800216e8`
- `0x180021770`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180021aea`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180021aea`
- `ntdll!EtwEventEnabled` at `0x1800217c4`
- `ntdll!EtwEventEnabled` at `0x180021855`
- `ntdll!EtwEventEnabled` at `0x180021aa1`
- `ntdll!EtwEventEnabled` at `0x1800217c4`
- `ntdll!EtwEventEnabled` at `0x180021855`
- `ntdll!EtwEventEnabled` at `0x180021aa1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002180e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002180e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021a8d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021a8d`

## string_xrefs

- `0x1800217ce`: `New thread started for UI invocation`
- `0x180021aae`: `Exiting thread created for third party UI invocation. ReturnCode = %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall thirdPartyUIInvocationThread(_DWORD *a1)
{
  HRESULT *v2; // r13
  struct IUnknown *v3; // rbx
  struct IUnknown *v4; // rdx
  unsigned int v5; // r12d
  _QWORD *v6; // r14
  ULONG (__stdcall *v7)(IUnknown *); // rsi
  __int64 *v8; // rcx
  __int64 v9; // rdi
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // r15
  __int64 *v14; // rcx
  __int64 v15; // r14
  int v16; // esi
  __int64 *v17; // rcx
  __int64 v18; // rdi
  int v19; // eax
  int v20; // eax
  __int64 v21; // r14
  ULONG (__stdcall *v22)(IUnknown *); // rsi
  __int64 *v23; // rcx
  __int64 v24; // rdi
  int v25; // eax
  int v26; // eax
  unsigned int v28; // [rsp+70h] [rbp-90h] BYREF
  void *v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v31; // [rsp+88h] [rbp-78h]
  struct IUnknown *v32[2]; // [rsp+90h] [rbp-70h] BYREF
  char v33[2048]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = a1 + 1;
  a1[1] = 1;
  v3 = 0;
  v32[0] = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v33, 0x800u, "New thread started for UI invocation") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v33);
  }
  v31 = CoInitializeEx(0, 2u);
  v4 = (struct IUnknown *)*CreateProxy(&v30, v2);
  if ( v4 )
  {
    ATL::AtlComPtrAssign(v32, v4);
    v3 = v32[0];
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v30);
  if ( *v2 >= 0 )
  {
    v5 = 0;
    if ( *a1 )
    {
      if ( *a1 == 1 )
      {
        v28 = 0;
        v29 = 0;
        v12 = *((_QWORD *)a1 + 1);
        v30 = v12;
        AddRef = v3->lpVtbl[2].AddRef;
        v14 = *(__int64 **)(v12 + 32);
        v15 = *v14;
        v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v14[1]);
        v17 = *(__int64 **)(v12 + 24);
        v18 = *v17;
        v19 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v17[1]);
        v20 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD, _QWORD, int, __int64, int, __int64, unsigned int *, void **, __int64, __int64))AddRef)(
                v3,
                v30,
                *(_QWORD *)(v30 + 40),
                *(unsigned int *)(v30 + 16),
                v19,
                v18,
                v16,
                v15,
                &v28,
                &v29,
                v30 + 64,
                v30 + 72);
        *v2 = v20;
        if ( v20 >= 0 )
          TempBuffer<0>::Assign(*(_QWORD *)(v30 + 48), v28, v29);
        else
          v5 = v20;
      }
      else
      {
        if ( *a1 != 2 )
          goto LABEL_26;
        v28 = 0;
        v29 = 0;
        v6 = (_QWORD *)*((_QWORD *)a1 + 1);
        v7 = v3->lpVtbl[4].AddRef;
        v8 = (__int64 *)v6[2];
        v9 = *v8;
        v10 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v8[1]);
        v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, _QWORD, _QWORD, __int64, unsigned int *, void **, _QWORD *))v7)(
                v3,
                v6,
                v6[3],
                v10,
                v9,
                &v28,
                &v29,
                v6 + 5);
        *v2 = v11;
        if ( v11 >= 0 )
          TempBuffer<0>::Assign(v6[4], v28, v29);
        else
          v5 = v11;
      }
    }
    else
    {
      v28 = 0;
      v29 = 0;
      v21 = *((_QWORD *)a1 + 1);
      v22 = v3->lpVtbl[1].AddRef;
      v23 = *(__int64 **)(v21 + 24);
      v24 = *v23;
      v25 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v23[1]);
      v26 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD, _QWORD, int, __int64, unsigned int *, void **, __int64))v22)(
              v3,
              v21,
              *(_QWORD *)(v21 + 32),
              *(unsigned int *)(v21 + 16),
              v25,
              v24,
              &v28,
              &v29,
              v21 + 48);
      *v2 = v26;
      if ( v26 >= 0 )
        TempBuffer<0>::Assign(*(_QWORD *)(v21 + 40), v28, v29);
      else
        v5 = v26;
    }
    com_ptr<unsigned char>::Clear(&v29);
  }
  else
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v33,
                0x800u,
                "New process could not be started for third party UI invocation. Failed with %x",
                *v2) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v33);
    }
    v5 = *v2;
  }
LABEL_26:
  if ( v31 <= 1 )
    CoUninitialize();
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v33, 0x800u, "Exiting thread created for third party UI invocation. ReturnCode = %x", v5) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v33);
  }
  _o__endthreadex(v5);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v32);
  return v5;
}

```

## disassembly

```asm
0x180021770  push    rbp
0x180021772  push    rbx
0x180021773  push    rsi
0x180021774  push    rdi
0x180021775  push    r12
0x180021777  push    r13
0x180021779  push    r14
0x18002177b  push    r15
0x18002177d  lea     rbp, [rsp-7B8h]
0x180021785  sub     rsp, 8B8h
0x18002178c  mov     rax, cs:__security_cookie
0x180021793  xor     rax, rsp
0x180021796  mov     [rbp+7F0h+var_50], rax
0x18002179d  mov     rdi, rcx
0x1800217a0  lea     r13, [rcx+4]
0x1800217a4  mov     dword ptr [r13+0], 1
0x1800217ac  xor     r15d, r15d
0x1800217af  mov     ebx, r15d
0x1800217b2  mov     [rbp+7F0h+var_860], rbx
0x1800217b6  lea     rdx, DebugInfoEvent
0x1800217bd  mov     rcx, cs:eaphost_Context
0x1800217c4  call    cs:__imp_EtwEventEnabled
0x1800217ca  test    al, al
0x1800217cc  jz      short loc_180021807
0x1800217ce  lea     r8, aNewThreadStart; "New thread started for UI invocation"
0x1800217d5  mov     edx, 800h; unsigned __int64
0x1800217da  lea     rcx, [rbp+7F0h+var_850]; char *
0x1800217de  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800217e3  test    eax, eax
0x1800217e5  js      short loc_180021807
0x1800217e7  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x1800217ee  jge     short loc_180021807
0x1800217f0  lea     r8, [rbp+7F0h+var_850]
0x1800217f4  lea     rdx, DebugInfoEvent
0x1800217fb  lea     rcx, eaphost_Context
0x180021802  call    McTemplateU0s_EtwEventWriteTransfer
0x180021807  mov     edx, 2; dwCoInit
0x18002180c  xor     ecx, ecx; pvReserved
0x18002180e  call    cs:__imp_CoInitializeEx
0x180021814  mov     [rbp+7F0h+var_868], eax
0x180021817  mov     rdx, r13
0x18002181a  lea     rcx, [rbp+7F0h+var_870]
0x18002181e  call    ?CreateProxy@@YA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@PEAJ@Z; CreateProxy(long *)
0x180021823  mov     rdx, [rax]; struct IUnknown *
0x180021826  test    rdx, rdx
0x180021829  jz      short loc_180021838
0x18002182b  lea     rcx, [rbp+7F0h+var_860]; struct IUnknown **
0x18002182f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180021834  mov     rbx, [rbp+7F0h+var_860]
0x180021838  lea     rcx, [rbp+7F0h+var_870]
0x18002183c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180021841  cmp     [r13+0], r15d
0x180021845  jge     short loc_1800218A5
0x180021847  lea     rdx, DebugErrorEvent
0x18002184e  mov     rcx, cs:eaphost_Context
0x180021855  call    cs:__imp_EtwEventEnabled
0x18002185b  test    al, al
0x18002185d  jz      short loc_18002189C
0x18002185f  mov     r9d, [r13+0]
0x180021863  lea     r8, aNewProcessCoul; "New process could not be started for th"...
0x18002186a  mov     edx, 800h; unsigned __int64
0x18002186f  lea     rcx, [rbp+7F0h+var_850]; char *
0x180021873  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180021878  test    eax, eax
0x18002187a  js      short loc_18002189C
0x18002187c  test    cs:byte_18004AF81, 8
0x180021883  jz      short loc_18002189C
0x180021885  lea     r8, [rbp+7F0h+var_850]
0x180021889  lea     rdx, DebugErrorEvent
0x180021890  lea     rcx, eaphost_Context
0x180021897  call    McTemplateU0s_EtwEventWriteTransfer
0x18002189c  mov     r12d, [r13+0]
0x1800218a0  jmp     loc_180021A87
0x1800218a5  mov     r12d, r15d
0x1800218a8  mov     ecx, [rdi]
0x1800218aa  test    ecx, ecx
0x1800218ac  jz      loc_1800219FC
0x1800218b2  sub     ecx, 1
0x1800218b5  jz      loc_180021944
0x1800218bb  cmp     ecx, 1
0x1800218be  jnz     loc_180021A87
0x1800218c4  mov     [rsp+8F0h+var_880], r15d
0x1800218c9  mov     [rsp+8F0h+var_878], r15
0x1800218ce  mov     r14, [rdi+8]
0x1800218d2  mov     rax, [rbx]
0x1800218d5  mov     rsi, [rax+68h]
0x1800218d9  mov     rcx, [r14+10h]
0x1800218dd  mov     rdi, [rcx]
0x1800218e0  mov     rcx, [rcx+8]
0x1800218e4  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800218e9  lea     rcx, [r14+28h]
0x1800218ed  mov     [rsp+8F0h+var_8B8], rcx
0x1800218f2  lea     rcx, [rsp+8F0h+var_878]
0x1800218f7  mov     [rsp+8F0h+var_8C0], rcx
0x1800218fc  lea     rcx, [rsp+8F0h+var_880]
0x180021901  mov     [rsp+8F0h+var_8C8], rcx
0x180021906  mov     [rsp+8F0h+var_8D0], rdi
0x18002190b  mov     r9d, eax
0x18002190e  mov     r8, [r14+18h]
0x180021912  mov     rdx, r14
0x180021915  mov     rcx, rbx
0x180021918  mov     rax, rsi
0x18002191b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021920  mov     [r13+0], eax
0x180021924  test    eax, eax
0x180021926  jns     short loc_180021930
0x180021928  mov     r12d, eax
0x18002192b  jmp     loc_180021A7D
0x180021930  mov     edx, [rsp+8F0h+var_880]
0x180021934  mov     r8, [rsp+8F0h+var_878]
0x180021939  mov     rcx, [r14+20h]
0x18002193d  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180021942  jmp     short loc_18002192B
0x180021944  mov     [rsp+8F0h+var_880], r15d
0x180021949  mov     [rsp+8F0h+var_878], r15
0x18002194e  mov     rdi, [rdi+8]
0x180021952  mov     [rbp+7F0h+var_870], rdi
0x180021956  mov     rax, [rbx]
0x180021959  mov     r15, [rax+38h]
0x18002195d  mov     rcx, [rdi+20h]
0x180021961  mov     r14, [rcx]
0x180021964  mov     rcx, [rcx+8]
0x180021968  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002196d  mov     esi, eax
0x18002196f  mov     rcx, [rdi+18h]
0x180021973  mov     rdi, [rcx]
0x180021976  mov     rcx, [rcx+8]
0x18002197a  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002197f  mov     r10, [rbp+7F0h+var_870]
0x180021983  lea     rcx, [r10+48h]
0x180021987  lea     rdx, [r10+40h]
0x18002198b  mov     [rsp+8F0h+var_898], rcx
0x180021990  mov     [rsp+8F0h+var_8A0], rdx
0x180021995  lea     rcx, [rsp+8F0h+var_878]
0x18002199a  mov     [rsp+8F0h+var_8A8], rcx
0x18002199f  lea     rcx, [rsp+8F0h+var_880]
0x1800219a4  mov     [rsp+8F0h+var_8B0], rcx
0x1800219a9  mov     [rsp+8F0h+var_8B8], r14
0x1800219ae  mov     dword ptr [rsp+8F0h+var_8C0], esi
0x1800219b2  mov     [rsp+8F0h+var_8C8], rdi
0x1800219b7  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x1800219bb  mov     r9d, [r10+10h]
0x1800219bf  mov     r8, [r10+28h]
0x1800219c3  mov     rdx, r10
0x1800219c6  mov     rcx, rbx
0x1800219c9  mov     rax, r15
0x1800219cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d1  mov     [r13+0], eax
0x1800219d5  xor     r15d, r15d
0x1800219d8  test    eax, eax
0x1800219da  jns     short loc_1800219E4
0x1800219dc  mov     r12d, eax
0x1800219df  jmp     loc_180021A7D
0x1800219e4  mov     edx, [rsp+8F0h+var_880]
0x1800219e8  mov     r8, [rsp+8F0h+var_878]
0x1800219ed  mov     rdi, [rbp+7F0h+var_870]
0x1800219f1  mov     rcx, [rdi+30h]
0x1800219f5  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800219fa  jmp     short loc_1800219DF
0x1800219fc  mov     [rsp+8F0h+var_880], r15d
0x180021a01  mov     [rsp+8F0h+var_878], r15
0x180021a06  mov     r14, [rdi+8]
0x180021a0a  mov     rax, [rbx]
0x180021a0d  mov     rsi, [rax+20h]
0x180021a11  mov     rcx, [r14+18h]
0x180021a15  mov     rdi, [rcx]
0x180021a18  mov     rcx, [rcx+8]
0x180021a1c  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180021a21  lea     rcx, [r14+30h]
0x180021a25  mov     [rsp+8F0h+var_8B0], rcx
0x180021a2a  lea     rcx, [rsp+8F0h+var_878]
0x180021a2f  mov     [rsp+8F0h+var_8B8], rcx
0x180021a34  lea     rcx, [rsp+8F0h+var_880]
0x180021a39  mov     [rsp+8F0h+var_8C0], rcx
0x180021a3e  mov     [rsp+8F0h+var_8C8], rdi
0x180021a43  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x180021a47  mov     r9d, [r14+10h]
0x180021a4b  mov     r8, [r14+20h]
0x180021a4f  mov     rdx, r14
0x180021a52  mov     rcx, rbx
0x180021a55  mov     rax, rsi
0x180021a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a5d  mov     [r13+0], eax
0x180021a61  test    eax, eax
0x180021a63  jns     short loc_180021A6A
0x180021a65  mov     r12d, eax
0x180021a68  jmp     short loc_180021A7D
0x180021a6a  mov     edx, [rsp+8F0h+var_880]
0x180021a6e  mov     r8, [rsp+8F0h+var_878]
0x180021a73  mov     rcx, [r14+28h]
0x180021a77  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180021a7c  nop
0x180021a7d  lea     rcx, [rsp+8F0h+var_878]
0x180021a82  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180021a87  cmp     [rbp+7F0h+var_868], 1
0x180021a8b  ja      short loc_180021A93
0x180021a8d  call    cs:__imp_CoUninitialize
0x180021a93  lea     rdx, DebugInfoEvent
0x180021a9a  mov     rcx, cs:eaphost_Context
0x180021aa1  call    cs:__imp_EtwEventEnabled
0x180021aa7  test    al, al
0x180021aa9  jz      short loc_180021AE7
0x180021aab  mov     r9d, r12d
0x180021aae  lea     r8, aExitingThreadC; "Exiting thread created for third party "...
0x180021ab5  mov     edx, 800h; unsigned __int64
0x180021aba  lea     rcx, [rbp+7F0h+var_850]; char *
0x180021abe  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180021ac3  test    eax, eax
0x180021ac5  js      short loc_180021AE7
0x180021ac7  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x180021ace  jge     short loc_180021AE7
0x180021ad0  lea     r8, [rbp+7F0h+var_850]
0x180021ad4  lea     rdx, DebugInfoEvent
0x180021adb  lea     rcx, eaphost_Context
0x180021ae2  call    McTemplateU0s_EtwEventWriteTransfer
0x180021ae7  mov     ecx, r12d
0x180021aea  call    cs:__imp__o__endthreadex
0x180021af0  nop
0x180021af1  lea     rcx, [rbp+7F0h+var_860]
0x180021af5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180021afa  mov     eax, r12d
0x180021afd  mov     rcx, [rbp+7F0h+var_50]
0x180021b04  xor     rcx, rsp; StackCookie
0x180021b07  call    __security_check_cookie
0x180021b0c  add     rsp, 8B8h
0x180021b13  pop     r15
0x180021b15  pop     r14
0x180021b17  pop     r13
0x180021b19  pop     r12
0x180021b1b  pop     rdi
0x180021b1c  pop     rsi
0x180021b1d  pop     rbx
0x180021b1e  pop     rbp
0x180021b1f  retn
```
