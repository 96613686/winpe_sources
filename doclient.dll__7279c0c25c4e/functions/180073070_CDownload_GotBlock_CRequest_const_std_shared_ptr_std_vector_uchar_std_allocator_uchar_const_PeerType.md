# CDownload::GotBlock(CRequest const &,std::shared_ptr<std::vector<uchar,std::allocator<uchar>>> const &,PeerType)

- ea: `0x180073070`
- end: `0x180073325`
- name: `?GotBlock@CDownload@@UEAAJAEBVCRequest@@AEBV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@W4PeerType@@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18007be30`

## callees

- `0x1800095a0`
- `0x18001eeac`
- `0x180055ab0`
- `0x1800642b8`
- `0x180071c08`
- `0x180072c7c`
- `0x180073070`
- `0x1800787d8`
- `0x180079018`
- `0x1800790b4`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800f8314`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800732ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800732ec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180073113`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800732fa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180073113`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800732fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDownload::GotBlock(__int64 a1, const struct CRequest *a2, __int64 a3, int a4)
{
  char v8; // bl
  HANDLE CurrentThread; // rax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  char v12; // di
  unsigned int v13; // r8d
  __int64 *v14; // rdx
  __int64 *v15; // rax
  __int64 *v16; // rcx
  __int64 *v17; // r15
  void **v18; // r10
  __int64 v19; // rax
  const char *v20; // r15
  __int64 v21; // rax
  const char *v22; // r9
  HANDLE v23; // rax
  __int64 result; // rax
  char v25; // [rsp+30h] [rbp-68h]
  void *Block; // [rsp+40h] [rbp-58h] BYREF
  char v27; // [rsp+48h] [rbp-50h]
  __int64 v28; // [rsp+50h] [rbp-48h] BYREF
  int v29; // [rsp+5Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 136) + 24LL))(*(_QWORD *)(a1 + 136)) )
  {
    LogMessage(2u, "CDownload::GotBlock", 0xD8u, "TelemetryAssert (%s): %s", "_conn.IsAwake()", "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  v8 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 112LL) + 8LL) + 352LL) + 644LL);
  v27 = v8;
  if ( v8 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  v10 = 0;
  Block = 0;
  CDownload::_FindRequest(a1, &Block, a2);
  try
  {
    v11 = Block;
    if ( Block == *(void **)(a1 + 8) )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 136) + 80LL))(*(_QWORD *)(a1 + 136));
      v20 = (const char *)v19;
      if ( *(_QWORD *)(v19 + 24) > 0xFu )
        v20 = *(const char **)v19;
      v21 = CRequest::Log(a2, &v28);
      if ( *(_QWORD *)(v21 + 24) > 0xFu )
        v21 = *(_QWORD *)v21;
      LogMessage(
        3u,
        "CDownload::GotBlock",
        0xFAu,
        "Received request %s that we didn't expect from %s",
        (const char *)v21,
        v20);
      std::string::~string(&v28);
    }
    else
    {
      v12 = *((_BYTE *)Block + 48);
      **((_QWORD **)Block + 1) = *(_QWORD *)Block;
      *(_QWORD *)(*v11 + 8LL) = v11[1];
      --*(_QWORD *)(a1 + 16);
      operator delete(v11);
      *(_QWORD *)(a1 + 144) = *(_QWORD *)std::chrono::steady_clock::now(&Block);
      v25 = v12;
      v10 = CDownloader::OnBlockArrived(*(_QWORD *)(a1 + 80), a2, a3, *(_QWORD *)(a1 + 136), a4, a1, v25);
      if ( (int)(v10 + 0x80000000) < 0 || v10 == -2133825529 )
      {
        v13 = *(_DWORD *)a2;
        v14 = *(__int64 **)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 120LL) + 8LL);
        v15 = (__int64 *)v14[1];
        v29 = 0;
        v16 = v14;
        while ( !*((_BYTE *)v15 + 25) )
        {
          if ( *((_DWORD *)v15 + 8) >= v13 )
            v16 = v15;
          else
            v15 += 2;
          v15 = (__int64 *)*v15;
        }
        if ( !*((_BYTE *)v16 + 25) && v13 >= *((_DWORD *)v16 + 8) && v16 != v14 )
        {
          v17 = v16 + 5;
          CPieceInformation::LostRequest((CPieceInformation *)(v16 + 5), a2);
          Block = 0;
          std::_Tree<std::_Tmap_traits<CRequest,unsigned int,std::less<CRequest>,std::allocator<std::pair<CRequest const,unsigned int>>,0>>::find(
            v17 + 5,
            &Block,
            a2);
          if ( Block == *v18 )
            *(_DWORD *)std::map<CRequest,unsigned int>::operator[](v18, a2) = 1;
          else
            ++*((_DWORD *)Block + 14);
        }
      }
      else
      {
        CPieceManager::LostRequest(*(CPieceManager **)(*(_QWORD *)(a1 + 80) + 120LL), a2);
      }
      if ( v10 + 2133825530 <= 1 )
        v10 = 0;
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, 0);
    if ( v8 )
    {
      v23 = GetCurrentThread();
      SetThreadPriority(v23, 0x20000);
    }
    result = v10;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x100,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\Download.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180073070  mov     [rsp+arg_18], rbx
0x180073075  push    rsi
0x180073076  push    rdi
0x180073077  push    r12
0x180073079  push    r14
0x18007307b  push    r15
0x18007307d  sub     rsp, 70h
0x180073081  mov     r15d, r9d
0x180073084  mov     r12, r8
0x180073087  mov     r14, rdx
0x18007308a  mov     rsi, rcx
0x18007308d  mov     rcx, [rcx+88h]
0x180073094  mov     rax, [rcx]
0x180073097  mov     rax, [rax+18h]
0x18007309b  call    _guard_dispatch_icall
0x1800730a0  test    al, al
0x1800730a2  jnz     short loc_1800730E4
0x1800730a4  lea     rax, aFailed; "Failed"
0x1800730ab  mov     [rsp+98h+var_70], rax
0x1800730b0  lea     rax, aConnIsawake; "_conn.IsAwake()"
0x1800730b7  mov     [rsp+98h+var_78], rax
0x1800730bc  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x1800730c3  mov     r8d, 0D8h; unsigned int
0x1800730c9  lea     rdx, aCdownloadGotbl; "CDownload::GotBlock"
0x1800730d0  mov     ecx, 2; unsigned __int8
0x1800730d5  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800730da  or      ecx, 0FFFFFFFFh; unsigned int
0x1800730dd  mov     edx, ecx; unsigned int
0x1800730df  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800730e4  mov     rax, [rsi+50h]
0x1800730e8  mov     rcx, [rax+70h]
0x1800730ec  mov     rax, [rcx+8]
0x1800730f0  mov     rbx, [rax+160h]
0x1800730f7  mov     bl, [rbx+284h]
0x1800730fd  mov     [rsp+98h+var_50], bl
0x180073101  test    bl, bl
0x180073103  jz      short loc_18007311A
0x180073105  call    cs:__imp_GetCurrentThread
0x18007310b  mov     rcx, rax; hThread
0x18007310e  mov     edx, 10000h; nPriority
0x180073113  call    cs:__imp_SetThreadPriority
0x180073119  nop
0x18007311a  xor     edi, edi
0x18007311c  mov     [rsp+98h+Block], rdi
0x180073121  mov     r8, r14
0x180073124  lea     rdx, [rsp+98h+Block]
0x180073129  mov     rcx, rsi
0x18007312c  call    ?_FindRequest@CDownload@@IEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@VCRequestBlock@@@std@@@std@@@std@@AEBVCRequest@@@Z; CDownload::_FindRequest(CRequest const &)
0x180073131  mov     rcx, [rsp+98h+Block]; Block
0x180073136  cmp     rcx, [rsi+8]
0x18007313a  jz      loc_18007326D
0x180073140  mov     dil, [rcx+30h]
0x180073144  mov     rdx, [rcx+8]
0x180073148  mov     rax, [rcx]
0x18007314b  mov     [rdx], rax
0x18007314e  mov     rdx, [rcx]
0x180073151  mov     rax, [rcx+8]
0x180073155  mov     [rdx+8], rax
0x180073159  dec     qword ptr [rsi+10h]
0x18007315d  mov     edx, 38h ; '8'
0x180073162  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073167  lea     rcx, [rsp+98h+Block]
0x18007316c  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180073171  mov     rcx, [rax]
0x180073174  mov     [rsi+90h], rcx
0x18007317b  mov     [rsp+98h+var_68], dil
0x180073180  mov     [rsp+98h+var_70], rsi
0x180073185  mov     dword ptr [rsp+98h+var_78], r15d
0x18007318a  mov     r9, [rsi+88h]
0x180073191  mov     r8, r12
0x180073194  mov     rdx, r14
0x180073197  mov     rcx, [rsi+50h]
0x18007319b  call    ?OnBlockArrived@CDownloader@@QEAAJAEBVCRequest@@AEBV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAVCPeerConn@@W4PeerType@@PEBVCDownload@@_N@Z; CDownloader::OnBlockArrived(CRequest const &,std::shared_ptr<std::vector<uchar>> const &,CPeerConn *,PeerType,CDownload const *,bool)
0x1800731a0  mov     edi, eax
0x1800731a2  mov     ecx, 80000000h
0x1800731a7  add     eax, ecx
0x1800731a9  test    ecx, eax
0x1800731ab  jnz     short loc_1800731CA
0x1800731ad  cmp     edi, 80D06807h
0x1800731b3  jz      short loc_1800731CA
0x1800731b5  mov     rcx, [rsi+50h]
0x1800731b9  mov     rdx, r14; struct CRequest *
0x1800731bc  mov     rcx, [rcx+78h]; this
0x1800731c0  call    ?LostRequest@CPieceManager@@QEAAXAEBVCRequest@@@Z; CPieceManager::LostRequest(CRequest const &)
0x1800731c5  jmp     loc_18007325E
0x1800731ca  mov     r8d, [r14]
0x1800731cd  mov     rax, [rsi+50h]
0x1800731d1  mov     rcx, [rax+78h]
0x1800731d5  mov     rdx, [rcx+8]
0x1800731d9  mov     rax, [rdx+8]
0x1800731dd  xor     ecx, ecx
0x1800731df  mov     [rsp+98h+var_3C], ecx
0x1800731e3  mov     rcx, rdx
0x1800731e6  jmp     short loc_1800731FA
0x1800731e8  cmp     [rax+20h], r8d
0x1800731ec  jnb     short loc_1800731F4
0x1800731ee  add     rax, 10h
0x1800731f2  jmp     short loc_1800731F7
0x1800731f4  mov     rcx, rax
0x1800731f7  mov     rax, [rax]
0x1800731fa  cmp     byte ptr [rax+19h], 0
0x1800731fe  jz      short loc_1800731E8
0x180073200  cmp     byte ptr [rcx+19h], 0
0x180073204  jnz     short loc_18007325E
0x180073206  cmp     r8d, [rcx+20h]
0x18007320a  jb      short loc_18007325E
0x18007320c  cmp     rcx, rdx
0x18007320f  jz      short loc_18007325E
0x180073211  lea     r15, [rcx+28h]
0x180073215  mov     rdx, r14; struct CRequest *
0x180073218  mov     rcx, r15; this
0x18007321b  call    ?LostRequest@CPieceInformation@@QEAAXAEBVCRequest@@@Z; CPieceInformation::LostRequest(CRequest const &)
0x180073220  mov     [rsp+98h+Block], 0
0x180073229  lea     r10, [r15+28h]
0x18007322d  mov     r8, r14
0x180073230  lea     rdx, [rsp+98h+Block]
0x180073235  mov     rcx, r10
0x180073238  call    ?find@?$_Tree@V?$_Tmap_traits@VCRequest@@IU?$less@VCRequest@@@std@@V?$allocator@U?$pair@$$CBVCRequest@@I@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCRequest@@I@std@@@std@@@std@@@2@AEBVCRequest@@@Z; std::_Tree<std::_Tmap_traits<CRequest,uint,std::less<CRequest>,std::allocator<std::pair<CRequest const,uint>>,0>>::find(CRequest const &)
0x18007323d  mov     r8, [rsp+98h+Block]
0x180073242  cmp     r8, [r10]
0x180073245  jz      short loc_18007324D
0x180073247  inc     dword ptr [r8+38h]
0x18007324b  jmp     short loc_18007325E
0x18007324d  mov     rdx, r14
0x180073250  mov     rcx, r10
0x180073253  call    ??A?$map@VCRequest@@IU?$less@VCRequest@@@std@@V?$allocator@U?$pair@$$CBVCRequest@@I@std@@@3@@std@@QEAAAEAIAEBVCRequest@@@Z; std::map<CRequest,uint>::operator[](CRequest const &)
0x180073258  mov     dword ptr [rax], 1
0x18007325e  lea     eax, [rdi+7F2F97FAh]
0x180073264  cmp     eax, 1
0x180073267  ja      short loc_1800732D6
0x180073269  xor     edi, edi
0x18007326b  jmp     short loc_1800732D6
0x18007326d  mov     rcx, [rsi+88h]
0x180073274  mov     rax, [rcx]
0x180073277  mov     rax, [rax+50h]
0x18007327b  call    _guard_dispatch_icall
0x180073280  mov     r15, rax
0x180073283  cmp     qword ptr [rax+18h], 0Fh
0x180073288  jbe     short loc_18007328D
0x18007328a  mov     r15, [rax]
0x18007328d  lea     rdx, [rsp+98h+var_48]
0x180073292  mov     rcx, r14
0x180073295  call    ?Log@CRequest@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CRequest::Log(void)
0x18007329a  cmp     qword ptr [rax+18h], 0Fh
0x18007329f  jbe     short loc_1800732A4
0x1800732a1  mov     rax, [rax]
0x1800732a4  mov     [rsp+98h+var_70], r15
0x1800732a9  mov     [rsp+98h+var_78], rax
0x1800732ae  lea     r9, aReceivedReques; "Received request %s that we didn't expe"...
0x1800732b5  mov     r8d, 0FAh; unsigned int
0x1800732bb  lea     rdx, aCdownloadGotbl; "CDownload::GotBlock"
0x1800732c2  mov     ecx, 3; unsigned __int8
0x1800732c7  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800732cc  lea     rcx, [rsp+98h+var_48]; void *
0x1800732d1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800732d6  mov     rax, [rsi]
0x1800732d9  xor     edx, edx
0x1800732db  mov     rcx, rsi
0x1800732de  mov     rax, [rax+40h]
0x1800732e2  call    _guard_dispatch_icall
0x1800732e7  nop
0x1800732e8  test    bl, bl
0x1800732ea  jz      short loc_180073300
0x1800732ec  call    cs:__imp_GetCurrentThread
0x1800732f2  mov     rcx, rax; hThread
0x1800732f5  mov     edx, 20000h; nPriority
0x1800732fa  call    cs:__imp_SetThreadPriority
0x180073300  mov     eax, edi
0x180073302  jmp     short loc_18007330F
0x180073304  mov     eax, 8007000Eh
0x180073309  jmp     short loc_18007330F
0x18007330b  mov     eax, dword ptr [rsp+98h+Block]
0x18007330f  mov     rbx, [rsp+98h+arg_18]
0x180073317  add     rsp, 70h
0x18007331b  pop     r15
0x18007331d  pop     r14
0x18007331f  pop     r12
0x180073321  pop     rdi
0x180073322  pop     rsi
0x180073323  retn
```
