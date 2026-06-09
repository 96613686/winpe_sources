# CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated(IAepDevnode *,long)

- ea: `0x18000e7d0`
- end: `0x18000ebce`
- name: `?OnDevnodeCreated@CWiGigDAFProviderDevnodeManagement@@QEAAJPEAUIAepDevnode@@J@Z`
- size: `1022`
- prototype: `__int64 __fastcall(DockCache **this, struct IAepDevnode *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18000e7c0`

## callees

- `0x18000c308`
- `0x18000c348`
- `0x18000cbc0`
- `0x18000e7d0`
- `0x18000ee64`
- `0x180010348`
- `0x180011808`
- `0x180011994`
- `0x180011c2c`
- `0x180011ee8`
- `0x180012110`
- `0x18001ca3e`
- `0x18001ca70`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e8f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e8f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb14`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated(
        DockCache **this,
        struct IAepDevnode *a2,
        int a3)
{
  _QWORD *v6; // rcx
  int v7; // eax
  unsigned __int16 *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // r12
  const unsigned __int16 *v10; // rdi
  int Dock; // edi
  char v12; // r13
  int v13; // r13d
  int ScanResultEvenIfStale; // edi
  int v15; // r12d
  _UNKNOWN **v16; // rcx
  const wchar_t *v17; // rax
  HANDLE ProcessHeap; // rax
  char v20; // [rsp+40h] [rbp-C0h]
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  Dock *v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[540]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+27Ch] [rbp+17Ch]
  unsigned __int16 v25[270]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v26[628]; // [rsp+6FCh] [rbp+5FCh] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, this);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_44;
  lpMem = 0;
  v7 = (*(__int64 (__fastcall **)(struct IAepDevnode *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &lpMem);
  if ( v7 >= 0 )
  {
    v8 = (unsigned __int16 *)lpMem;
    v22[1] = (Dock *)lpMem;
    memset_0(v25, 0, 0x488u);
    memset_0(v23, 0, 0x480u);
    DockCache::DevnodeCreated(this[78], v8, a2, a3);
    v9 = (struct _RTL_CRITICAL_SECTION *)this[78];
    v10 = (const unsigned __int16 *)lpMem;
    EnterCriticalSection(v9);
    v22[0] = 0;
    Dock = DockCache::FindDock((DockCache *)v9, v10, v22);
    if ( Dock < 0 )
    {
      LeaveCriticalSection(v9);
      goto LABEL_10;
    }
    v20 = *((_BYTE *)v22[0] + 586);
    v12 = *((_BYTE *)v22[0] + 2912);
    Dock = Dock::GetProfile(v22[0], (struct _DOCK_PROFILE *)v25);
    LeaveCriticalSection(v9);
    if ( Dock < 0 )
    {
LABEL_10:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
          (_DWORD)this,
          (__int64)lpMem,
          Dock);
        v6 = WPP_GLOBAL_Control;
      }
      if ( a3 >= 0 )
        a3 = Dock;
      goto LABEL_33;
    }
    if ( v12 || (v13 = 0, v20) )
      v13 = 1;
    ScanResultEvenIfStale = DockCache::GetScanResultEvenIfStale(
                              this[78],
                              (const unsigned __int16 *)lpMem,
                              (struct _VISIBLE_DOCK *)v23);
    if ( ScanResultEvenIfStale >= 0 )
    {
      v15 = v24;
    }
    else
    {
      v15 = 0;
      v16 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_32:
        v22[0] = 0;
        DockingDevnodeHelpers::RegisterInterface(
          &stru_1800262D8,
          v25,
          (const struct _MANUFACTURER_INFO *)v26,
          a2,
          a3,
          v13,
          v15,
          v22);
        DockCache::DeviceInterfaceRegistered(this[78], (const unsigned __int16 *)lpMem, v22[0]);
        (*(void (__fastcall **)(Dock *))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
        v6 = WPP_GLOBAL_Control;
LABEL_33:
        if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 3u && (*((_BYTE *)v6 + 28) & 1) != 0 )
        {
          WPP_SF_qSd(
            v6[2],
            18,
            (unsigned int)&WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
            (_DWORD)this,
            (__int64)lpMem,
            a3);
          v6 = WPP_GLOBAL_Control;
        }
        if ( !v8 )
          goto LABEL_44;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        goto LABEL_43;
      }
      if ( !*((_BYTE *)WPP_GLOBAL_Control + 25) || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_26:
        if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
        {
          v17 = L"disallowed";
          if ( v15 != 1 )
            v17 = (const wchar_t *)L"allowed";
          WPP_SF_qSlSd((TRACEHANDLE)v16[2], (__int64)lpMem, v13, (__int64)v17, ScanResultEvenIfStale);
        }
        goto LABEL_32;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
        this,
        ScanResultEvenIfStale);
    }
    v16 = (_UNKNOWN **)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (*(__int64 (__fastcall **)(DockCache *, _QWORD))(*(_QWORD *)this[76] + 24LL))(this[76], (unsigned int)a3);
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, this, v7);
LABEL_43:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_44:
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 4u && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_q(v6[2], 20, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, this);
  return (*(__int64 (__fastcall **)(DockCache *, _QWORD))(*(_QWORD *)this[76] + 24LL))(this[76], (unsigned int)a3);
}

```

## disassembly

```asm
0x18000e7d0  mov     [rsp-8+arg_18], rbx
0x18000e7d5  push    rbp
0x18000e7d6  push    rsi
0x18000e7d7  push    rdi
0x18000e7d8  push    r12
0x18000e7da  push    r13
0x18000e7dc  push    r14
0x18000e7de  push    r15
0x18000e7e0  lea     rbp, [rsp-880h]
0x18000e7e8  sub     rsp, 980h
0x18000e7ef  mov     rax, cs:__security_cookie
0x18000e7f6  xor     rax, rsp
0x18000e7f9  mov     [rbp+8B0h+var_40], rax
0x18000e800  mov     r15d, r8d
0x18000e803  mov     r14, rdx
0x18000e806  mov     rsi, rcx
0x18000e809  lea     r13, WPP_GLOBAL_Control
0x18000e810  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e817  cmp     rcx, r13
0x18000e81a  jz      short loc_18000E847
0x18000e81c  cmp     byte ptr [rcx+19h], 4
0x18000e820  jb      short loc_18000E847
0x18000e822  test    byte ptr [rcx+1Ch], 1
0x18000e826  jz      short loc_18000E847
0x18000e828  mov     edx, 0Eh
0x18000e82d  mov     r9, rsi
0x18000e830  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000e837  mov     rcx, [rcx+10h]
0x18000e83b  call    WPP_SF_q
0x18000e840  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e847  test    r14, r14
0x18000e84a  jz      loc_18000EB65
0x18000e850  mov     [rsp+9B0h+lpMem], 0
0x18000e859  mov     rax, [r14]
0x18000e85c  lea     rdx, [rsp+9B0h+lpMem]
0x18000e861  mov     rcx, r14
0x18000e864  mov     rax, [rax+28h]
0x18000e868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e86d  test    eax, eax
0x18000e86f  js      loc_18000EB2A
0x18000e875  mov     rbx, [rsp+9B0h+lpMem]
0x18000e87a  mov     [rsp+9B0h+var_958], rbx
0x18000e87f  xor     edx, edx; Val
0x18000e881  mov     r8d, 488h; Size
0x18000e887  lea     rcx, [rbp+8B0h+var_4D0]; void *
0x18000e88e  call    memset_0
0x18000e893  xor     edx, edx; Val
0x18000e895  mov     r8d, 480h; Size
0x18000e89b  lea     rcx, [rsp+9B0h+var_950]; void *
0x18000e8a0  call    memset_0
0x18000e8a5  mov     r9d, r15d; int
0x18000e8a8  mov     r8, r14; struct IAepDevnode *
0x18000e8ab  mov     rdx, rbx; unsigned __int16 *
0x18000e8ae  mov     rcx, [rsi+270h]; this
0x18000e8b5  call    ?DevnodeCreated@DockCache@@QEAAXPEBGPEAUIAepDevnode@@J@Z; DockCache::DevnodeCreated(ushort const *,IAepDevnode *,long)
0x18000e8ba  mov     r12, [rsi+270h]
0x18000e8c1  mov     rdi, [rsp+9B0h+lpMem]
0x18000e8c6  mov     rcx, r12; lpCriticalSection
0x18000e8c9  call    cs:__imp_EnterCriticalSection
0x18000e8cf  mov     [rsp+9B0h+var_960], 0
0x18000e8d8  lea     r8, [rsp+9B0h+var_960]; struct Dock **
0x18000e8dd  mov     rdx, rdi; unsigned __int16 *
0x18000e8e0  mov     rcx, r12; this
0x18000e8e3  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x18000e8e8  mov     edi, eax
0x18000e8ea  test    eax, eax
0x18000e8ec  jns     short loc_18000E8F9
0x18000e8ee  mov     rcx, r12; lpCriticalSection
0x18000e8f1  call    cs:__imp_LeaveCriticalSection
0x18000e8f7  jmp     short loc_18000E931
0x18000e8f9  mov     rcx, [rsp+9B0h+var_960]; this
0x18000e8fe  mov     al, [rcx+24Ah]
0x18000e904  mov     [rsp+9B0h+var_970], al
0x18000e908  mov     r13b, [rcx+0B60h]
0x18000e90f  lea     rdx, [rbp+8B0h+var_4D0]; struct _DOCK_PROFILE *
0x18000e916  call    ?GetProfile@Dock@@QEAAJPEAU_DOCK_PROFILE@@@Z; Dock::GetProfile(_DOCK_PROFILE *)
0x18000e91b  mov     edi, eax
0x18000e91d  mov     rcx, r12; lpCriticalSection
0x18000e920  call    cs:__imp_LeaveCriticalSection
0x18000e926  test    edi, edi
0x18000e928  jns     short loc_18000E987
0x18000e92a  lea     r13, WPP_GLOBAL_Control
0x18000e931  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e938  cmp     rcx, r13
0x18000e93b  jz      short loc_18000E976
0x18000e93d  cmp     byte ptr [rcx+19h], 1
0x18000e941  jb      short loc_18000E976
0x18000e943  test    byte ptr [rcx+1Ch], 1
0x18000e947  jz      short loc_18000E976
0x18000e949  mov     edx, 0Fh
0x18000e94e  mov     dword ptr [rsp+9B0h+var_988], edi
0x18000e952  mov     rax, [rsp+9B0h+lpMem]
0x18000e957  mov     [rsp+9B0h+var_990], rax
0x18000e95c  mov     r9, rsi
0x18000e95f  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000e966  mov     rcx, [rcx+10h]
0x18000e96a  call    WPP_SF_qSd
0x18000e96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e976  test    r15d, r15d
0x18000e979  js      loc_18000EAD0
0x18000e97f  mov     r15d, edi
0x18000e982  jmp     loc_18000EAD0
0x18000e987  test    r13b, r13b
0x18000e98a  jnz     short loc_18000E996
0x18000e98c  xor     r13d, r13d
0x18000e98f  cmp     [rsp+9B0h+var_970], r13b
0x18000e994  jz      short loc_18000E99C
0x18000e996  mov     r13d, 1
0x18000e99c  lea     r8, [rsp+9B0h+var_950]; struct _VISIBLE_DOCK *
0x18000e9a1  mov     rdx, [rsp+9B0h+lpMem]; unsigned __int16 *
0x18000e9a6  mov     rcx, [rsi+270h]; this
0x18000e9ad  call    ?GetScanResultEvenIfStale@DockCache@@QEAAJPEBGPEAU_VISIBLE_DOCK@@@Z; DockCache::GetScanResultEvenIfStale(ushort const *,_VISIBLE_DOCK *)
0x18000e9b2  mov     edi, eax
0x18000e9b4  test    eax, eax
0x18000e9b6  jns     short loc_18000E9FC
0x18000e9b8  xor     r12d, r12d
0x18000e9bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9c2  lea     rax, WPP_GLOBAL_Control
0x18000e9c9  cmp     rcx, rax
0x18000e9cc  jz      loc_18000EA5C
0x18000e9d2  cmp     byte ptr [rcx+19h], 1
0x18000e9d6  jb      short loc_18000EA11
0x18000e9d8  test    byte ptr [rcx+1Ch], 1
0x18000e9dc  jz      short loc_18000EA11
0x18000e9de  lea     edx, [r12+10h]
0x18000e9e3  mov     dword ptr [rsp+9B0h+var_990], edi
0x18000e9e7  mov     r9, rsi
0x18000e9ea  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000e9f1  mov     rcx, [rcx+10h]
0x18000e9f5  call    WPP_SF_qD
0x18000e9fa  jmp     short loc_18000EA03
0x18000e9fc  mov     r12d, [rbp+8B0h+var_734]
0x18000ea03  lea     rax, WPP_GLOBAL_Control
0x18000ea0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea11  cmp     rcx, rax
0x18000ea14  jz      short loc_18000EA5C
0x18000ea16  cmp     byte ptr [rcx+19h], 3
0x18000ea1a  jb      short loc_18000EA5C
0x18000ea1c  test    byte ptr [rcx+1Ch], 1
0x18000ea20  jz      short loc_18000EA5C
0x18000ea22  lea     rdx, aAllowed; "allowed"
0x18000ea29  lea     rax, aDisallowed; "disallowed"
0x18000ea30  cmp     r12d, 1
0x18000ea34  cmovnz  rax, rdx
0x18000ea38  mov     dword ptr [rsp+9B0h+var_978], edi; char
0x18000ea3c  mov     [rsp+9B0h+var_980], rax; __int64
0x18000ea41  mov     dword ptr [rsp+9B0h+var_988], r13d; char
0x18000ea46  mov     rax, [rsp+9B0h+lpMem]
0x18000ea4b  mov     [rsp+9B0h+var_990], rax; __int64
0x18000ea50  mov     r9, rsi
0x18000ea53  mov     rcx, [rcx+10h]; LoggerHandle
0x18000ea57  call    WPP_SF_qSlSd
0x18000ea5c  mov     [rsp+9B0h+var_960], 0
0x18000ea65  lea     rax, [rsp+9B0h+var_960]
0x18000ea6a  mov     [rsp+9B0h+var_978], rax; struct IAepDevnodeInterface **
0x18000ea6f  mov     dword ptr [rsp+9B0h+var_980], r12d; int
0x18000ea74  mov     dword ptr [rsp+9B0h+var_988], r13d; int
0x18000ea79  mov     dword ptr [rsp+9B0h+var_990], r15d; int
0x18000ea7e  mov     r9, r14; struct IAepDevnode *
0x18000ea81  lea     r8, [rbp+8B0h+var_2B4]; struct _MANUFACTURER_INFO *
0x18000ea88  lea     rdx, [rbp+8B0h+var_4D0]; unsigned __int16 *
0x18000ea8f  lea     rcx, stru_1800262D8; struct _GUID *
0x18000ea96  call    ?RegisterInterface@DockingDevnodeHelpers@@SAJAEBU_GUID@@PEBGAEBU_MANUFACTURER_INFO@@PEAUIAepDevnode@@JHHPEAPEAUIAepDevnodeInterface@@@Z; DockingDevnodeHelpers::RegisterInterface(_GUID const &,ushort const *,_MANUFACTURER_INFO const &,IAepDevnode *,long,int,int,IAepDevnodeInterface * *)
0x18000ea9b  mov     r8, [rsp+9B0h+var_960]; struct IAepDevnodeInterface *
0x18000eaa0  mov     rdx, [rsp+9B0h+lpMem]; unsigned __int16 *
0x18000eaa5  mov     rcx, [rsi+270h]; this
0x18000eaac  call    ?DeviceInterfaceRegistered@DockCache@@QEAAXPEBGPEAUIAepDevnodeInterface@@@Z; DockCache::DeviceInterfaceRegistered(ushort const *,IAepDevnodeInterface *)
0x18000eab1  mov     rcx, [rsp+9B0h+var_960]
0x18000eab6  mov     rax, [rcx]
0x18000eab9  mov     rax, [rax+10h]
0x18000eabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eac9  lea     r13, WPP_GLOBAL_Control
0x18000ead0  cmp     rcx, r13
0x18000ead3  jz      short loc_18000EB0F
0x18000ead5  cmp     byte ptr [rcx+19h], 3
0x18000ead9  jb      short loc_18000EB0F
0x18000eadb  test    byte ptr [rcx+1Ch], 1
0x18000eadf  jz      short loc_18000EB0F
0x18000eae1  mov     edx, 12h
0x18000eae6  mov     dword ptr [rsp+9B0h+var_988], r15d
0x18000eaeb  mov     rax, [rsp+9B0h+lpMem]
0x18000eaf0  mov     [rsp+9B0h+var_990], rax
0x18000eaf5  mov     r9, rsi
0x18000eaf8  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000eaff  mov     rcx, [rcx+10h]
0x18000eb03  call    WPP_SF_qSd
0x18000eb08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb0f  test    rbx, rbx
0x18000eb12  jz      short loc_18000EB65
0x18000eb14  call    cs:__imp_GetProcessHeap
0x18000eb1a  mov     r8, rbx; lpMem
0x18000eb1d  xor     edx, edx; dwFlags
0x18000eb1f  mov     rcx, rax; hHeap
0x18000eb22  call    cs:__imp_HeapFree
0x18000eb28  jmp     short loc_18000EB5E
0x18000eb2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb31  cmp     rcx, r13
0x18000eb34  jz      short loc_18000EB8E
0x18000eb36  cmp     byte ptr [rcx+19h], 1
0x18000eb3a  jb      short loc_18000EB65
0x18000eb3c  test    byte ptr [rcx+1Ch], 1
0x18000eb40  jz      short loc_18000EB65
0x18000eb42  mov     edx, 13h
0x18000eb47  mov     dword ptr [rsp+9B0h+var_990], eax
0x18000eb4b  mov     r9, rsi
0x18000eb4e  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000eb55  mov     rcx, [rcx+10h]
0x18000eb59  call    WPP_SF_qD
0x18000eb5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb65  cmp     rcx, r13
0x18000eb68  jz      short loc_18000EB8E
0x18000eb6a  cmp     byte ptr [rcx+19h], 4
0x18000eb6e  jb      short loc_18000EB8E
0x18000eb70  test    byte ptr [rcx+1Ch], 1
0x18000eb74  jz      short loc_18000EB8E
0x18000eb76  mov     edx, 14h
0x18000eb7b  mov     r9, rsi
0x18000eb7e  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000eb85  mov     rcx, [rcx+10h]
0x18000eb89  call    WPP_SF_q
0x18000eb8e  mov     rcx, [rsi+260h]
0x18000eb95  mov     rax, [rcx]
0x18000eb98  mov     edx, r15d
0x18000eb9b  mov     rax, [rax+18h]
0x18000eb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba4  mov     rcx, [rbp+8B0h+var_40]
0x18000ebab  xor     rcx, rsp; StackCookie
0x18000ebae  call    __security_check_cookie
0x18000ebb3  mov     rbx, [rsp+9B0h+arg_18]
0x18000ebbb  add     rsp, 980h
0x18000ebc2  pop     r15
0x18000ebc4  pop     r14
0x18000ebc6  pop     r13
0x18000ebc8  pop     r12
0x18000ebca  pop     rdi
0x18000ebcb  pop     rsi
0x18000ebcc  pop     rbp
0x18000ebcd  retn
```
