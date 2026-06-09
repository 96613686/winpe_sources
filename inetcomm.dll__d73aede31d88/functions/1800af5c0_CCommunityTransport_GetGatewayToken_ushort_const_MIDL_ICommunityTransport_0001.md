# CCommunityTransport::GetGatewayToken(ushort const *,__MIDL_ICommunityTransport_0001)

- ea: `0x1800af5c0`
- end: `0x1800af774`
- name: `?GetGatewayToken@CCommunityTransport@@UEAAJPEBGW4__MIDL_ICommunityTransport_0001@@@Z`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800055bc`
- `0x180022420`
- `0x1800a67ac`
- `0x1800a694c`
- `0x1800a6f84`
- `0x1800a77dc`
- `0x1800af5c0`
- `0x1800b1ad4`
- `0x1800c9fe8`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x1800af6d4`
- `KERNEL32!CompareStringA` at `0x1800af6d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800af751`
- `KERNEL32!LeaveCriticalSection` at `0x1800af751`
- `KERNEL32!EnterCriticalSection` at `0x1800af62e`
- `KERNEL32!EnterCriticalSection` at `0x1800af62e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af5fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af5fe`

## string_xrefs

- `0x1800af696`: `<?xml version="1.0" encoding="utf-8"?><soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><soap:Body><GetUsernameToken xmlns="http://www.microsoft.com/2003/mscom/Gateway"><ServiceName>%s</ServiceName><AppUsername>%s</AppUsername><AppPassword>%s</AppPassword><PersistToken>true</PersistToken></GetUsernameToken></soap:Body></soap:Envelope>`
- `0x1800af723`: `Content-type: text/xml; charset=utf-8\nSOAPAction: "http://www.microsoft.com/2003/mscom/Gateway/GetUsernameToken"\n`

## pseudocode

```c
__int64 __fastcall CCommunityTransport::GetGatewayToken(__int64 a1, const unsigned __int16 *a2, int a3)
{
  OLECHAR *v7; // rcx
  CAsyncHttp *v8; // rcx
  int v9; // edi
  char *v10; // rsi
  int v11; // eax
  __int16 v12; // r8
  int lpString2; // [rsp+20h] [rbp-38h]

  if ( !a2 )
    return 2147942487LL;
  if ( !*(_QWORD *)(a1 + 40) )
    return 2148322316LL;
  v7 = *(OLECHAR **)(a1 + 3912);
  if ( v7 )
  {
    SysFreeString(v7);
    *(_QWORD *)(a1 + 3912) = 0;
  }
  v8 = *(CAsyncHttp **)(a1 + 40);
  if ( *((_DWORD *)v8 + 26) && *((_DWORD *)v8 + 26) != 10 )
    CAsyncHttp::Close(v8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 3928));
  *(_DWORD *)(a1 + 32) = 8;
  *(_DWORD *)(a1 + 13120) = a3;
  v9 = StringCchCopyW((unsigned __int16 *)(a1 + 2412), 0x100u, a2);
  if ( v9 >= 0 )
  {
    v10 = (char *)ZeroAllocate(0x1FCu);
    if ( v10 )
    {
      v9 = StringCchPrintfA(
             v10,
             0x1FCu,
             "<?xml version=\"1.0\" encoding=\"utf-8\"?><soap:Envelope xmlns:soap=\"http://schemas.xmlsoap.org/soap/envel"
             "ope/\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http://www.w3.org/2001/XMLSchema"
             "\"><soap:Body><GetUsernameToken xmlns=\"http://www.microsoft.com/2003/mscom/Gateway\"><ServiceName>%s</Serv"
             "iceName><AppUsername>%s</AppUsername><AppPassword>%s</AppPassword><PersistToken>true</PersistToken></GetUse"
             "rnameToken></soap:Body></soap:Envelope>",
             "CmtyAPI",
             "NaVqcSKAV71Xwe5v/zgIAc22Hbg183KP",
             "bdd3e8e8-");
      if ( v9 >= 0 )
      {
        v11 = CompareStringA(0x7Fu, 1u, (PCNZCH)(a1 + 12170), -1, "https", -1);
        v12 = 443;
        if ( v11 != 2 )
          v12 = 80;
        v9 = CAsyncHttp::HrInit(*(CAsyncHttp **)(a1 + 40), (char *)(a1 + 9098), v12, 0);
        if ( v9 >= 0 )
        {
          v9 = CAsyncHttp::Connect(*(_QWORD *)(a1 + 40));
          if ( v9 >= 0 )
            v9 = CAsyncHttp::SubmitRequestToServer(
                   *(CAsyncHttp **)(a1 + 40),
                   (const char *)(a1 + 10122),
                   "Content-type: text/xml; charset=utf-8\r\n"
                   "SOAPAction: \"http://www.microsoft.com/2003/mscom/Gateway/GetUsernameToken\"\r\n",
                   v10,
                   lpString2);
        }
      }
      ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v10);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3928));
  if ( v9 != -2147483638 )
    CCommunityTransport::SetComplete((CCommunityTransport *)a1, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800af5c0  push    rbx
0x1800af5c2  push    rbp
0x1800af5c3  push    rsi
0x1800af5c4  push    rdi
0x1800af5c5  sub     rsp, 38h
0x1800af5c9  mov     esi, r8d
0x1800af5cc  mov     rdi, rdx
0x1800af5cf  mov     rbx, rcx
0x1800af5d2  test    rdx, rdx
0x1800af5d5  jnz     short loc_1800AF5E1
0x1800af5d7  mov     eax, 80070057h
0x1800af5dc  jmp     loc_1800AF76B
0x1800af5e1  cmp     qword ptr [rcx+28h], 0
0x1800af5e6  jnz     short loc_1800AF5F2
0x1800af5e8  mov     eax, 800CCC0Ch
0x1800af5ed  jmp     loc_1800AF76B
0x1800af5f2  mov     rcx, [rcx+0F48h]; bstrString
0x1800af5f9  test    rcx, rcx
0x1800af5fc  jz      short loc_1800AF60F
0x1800af5fe  call    cs:__imp_SysFreeString
0x1800af604  mov     qword ptr [rbx+0F48h], 0
0x1800af60f  mov     rcx, [rbx+28h]; this
0x1800af613  cmp     dword ptr [rcx+68h], 0
0x1800af617  jz      short loc_1800AF624
0x1800af619  cmp     dword ptr [rcx+68h], 0Ah
0x1800af61d  jz      short loc_1800AF624
0x1800af61f  call    ?Close@CAsyncHttp@@QEAAJXZ; CAsyncHttp::Close(void)
0x1800af624  lea     rbp, [rbx+0F58h]
0x1800af62b  mov     rcx, rbp; lpCriticalSection
0x1800af62e  call    cs:__imp_EnterCriticalSection
0x1800af634  lea     rcx, [rbx+96Ch]; unsigned __int16 *
0x1800af63b  mov     dword ptr [rbx+20h], 8
0x1800af642  mov     r8, rdi; unsigned __int16 *
0x1800af645  mov     [rbx+3340h], esi
0x1800af64b  mov     edx, 100h; unsigned __int64
0x1800af650  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800af655  mov     edi, eax
0x1800af657  test    eax, eax
0x1800af659  js      loc_1800AF74E
0x1800af65f  mov     edi, 1FCh
0x1800af664  mov     ecx, edi; Size
0x1800af666  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x1800af66b  mov     rsi, rax
0x1800af66e  test    rax, rax
0x1800af671  jz      loc_1800AF749
0x1800af677  lea     rax, aBdd3e8e8; "bdd3e8e8-"
0x1800af67e  mov     edx, edi; unsigned __int64
0x1800af680  mov     qword ptr [rsp+58h+cchCount2], rax
0x1800af685  lea     r9, aCmtyapi; "CmtyAPI"
0x1800af68c  lea     rax, aNavqcskav71xwe; "NaVqcSKAV71Xwe5v/zgIAc22Hbg183KP"
0x1800af693  mov     rcx, rsi; char *
0x1800af696  lea     r8, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x1800af69d  mov     [rsp+58h+lpString2], rax
0x1800af6a2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800af6a7  mov     edi, eax
0x1800af6a9  test    eax, eax
0x1800af6ab  js      loc_1800AF731
0x1800af6b1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800af6b5  lea     rax, aHttps; "https"
0x1800af6bc  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800af6c1  lea     r8, [rbx+2F8Ah]; lpString1
0x1800af6c8  mov     [rsp+58h+lpString2], rax; int
0x1800af6cd  lea     edx, [r9+2]; dwCmpFlags
0x1800af6d1  lea     ecx, [rdx+7Eh]; Locale
0x1800af6d4  call    cs:__imp_CompareStringA
0x1800af6da  mov     ecx, 50h ; 'P'
0x1800af6df  lea     rdx, [rbx+238Ah]; char *
0x1800af6e6  cmp     eax, 2
0x1800af6e9  mov     r8d, 1BBh
0x1800af6ef  cmovnz  r8w, cx; unsigned __int16
0x1800af6f4  mov     rcx, [rbx+28h]; this
0x1800af6f8  xor     r9d, r9d; unsigned int
0x1800af6fb  call    ?HrInit@CAsyncHttp@@QEAAJPEADGK@Z; CAsyncHttp::HrInit(char *,ushort,ulong)
0x1800af700  mov     edi, eax
0x1800af702  test    eax, eax
0x1800af704  js      short loc_1800AF731
0x1800af706  mov     rcx, [rbx+28h]; dwContext
0x1800af70a  call    ?Connect@CAsyncHttp@@QEAAJXZ; CAsyncHttp::Connect(void)
0x1800af70f  mov     edi, eax
0x1800af711  test    eax, eax
0x1800af713  js      short loc_1800AF731
0x1800af715  mov     rcx, [rbx+28h]; this
0x1800af719  lea     rdx, [rbx+278Ah]; char *
0x1800af720  mov     r9, rsi; char *
0x1800af723  lea     r8, aContentTypeTex; "Content-type: text/xml; charset=utf-8\r"...
0x1800af72a  call    ?SubmitRequestToServer@CAsyncHttp@@QEAAJPEBD00H@Z; CAsyncHttp::SubmitRequestToServer(char const *,char const *,char const *,int)
0x1800af72f  mov     edi, eax
0x1800af731  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800af738  mov     rdx, rsi
0x1800af73b  mov     rax, [rcx]
0x1800af73e  mov     rax, [rax+28h]
0x1800af742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af747  jmp     short loc_1800AF74E
0x1800af749  mov     edi, 8007000Eh
0x1800af74e  mov     rcx, rbp; lpCriticalSection
0x1800af751  call    cs:__imp_LeaveCriticalSection
0x1800af757  cmp     edi, 8000000Ah
0x1800af75d  jz      short loc_1800AF769
0x1800af75f  mov     edx, edi; int
0x1800af761  mov     rcx, rbx; this
0x1800af764  call    ?SetComplete@CCommunityTransport@@AEAAXJ@Z; CCommunityTransport::SetComplete(long)
0x1800af769  mov     eax, edi
0x1800af76b  add     rsp, 38h
0x1800af76f  pop     rdi
0x1800af770  pop     rsi
0x1800af771  pop     rbp
0x1800af772  pop     rbx
0x1800af773  retn
```
