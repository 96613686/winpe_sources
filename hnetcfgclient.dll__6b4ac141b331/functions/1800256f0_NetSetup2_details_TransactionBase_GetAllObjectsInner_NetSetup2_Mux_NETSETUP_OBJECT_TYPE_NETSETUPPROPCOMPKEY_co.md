# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::Mux>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x1800256f0`
- end: `0x1800258bd`
- name: `??$GetAllObjectsInner@VMux@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `461`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026b3c`

## callees

- `0x180001274`
- `0x1800215a4`
- `0x1800256f0`
- `0x180025e0c`
- `0x180026c18`
- `0x180026f34`
- `0x180027064`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180025890`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025890`
- `NetSetupApi!NetSetupGetObjects` at `0x180025767`
- `NetSetupApi!NetSetupGetObjects` at `0x180025767`

## pseudocode

```c
_QWORD *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::Mux>(_QWORD *a1, _QWORD *a2)
{
  int Objects; // eax
  int v5; // [rsp+60h] [rbp-18h] BYREF
  __int64 v6; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  Objects = NetSetupGetObjects(*a1, 8, 0);
  if ( Objects < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x498,
      (unsigned int)"onecore\\internal\\net\\inc\\netsetupcxx.h",
      (const char *)(unsigned int)Objects,
      0);
  v5 = 0;
  v6 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  NetSetup2::details::AutoFreeObjects::~AutoFreeObjects((NetSetup2::details::AutoFreeObjects *)&v5);
  return a2;
}

```

## disassembly

```asm
0x1800256f0  mov     r11, rsp
0x1800256f3  mov     [r11+20h], r9
0x1800256f7  mov     [r11+18h], r8d
0x1800256fb  mov     [r11+10h], rdx
0x1800256ff  push    rbp
0x180025700  push    rbx
0x180025701  push    rsi
0x180025702  push    rdi
0x180025703  push    r14
0x180025705  push    r15
0x180025707  mov     rbp, rsp
0x18002570a  sub     rsp, 78h
0x18002570e  mov     rbx, rdx
0x180025711  mov     r15, rcx
0x180025714  mov     [rbp+var_28], 0
0x18002571b  mov     [rbp+arg_10], 0
0x180025722  mov     [rbp+arg_18], 0
0x18002572a  lea     rax, [rbp+arg_18]
0x18002572e  mov     [r11-60h], rax
0x180025732  lea     rax, [rbp+arg_10]
0x180025736  mov     [r11-68h], rax
0x18002573a  mov     rax, [rbp+arg_28]
0x18002573e  mov     [r11-70h], rax
0x180025742  mov     [rsp+78h+var_48], 1
0x18002574a  mov     qword ptr [r11-80h], 0
0x180025752  mov     [rsp+78h+var_58], 0; int
0x18002575a  xor     r9d, r9d
0x18002575d  xor     r8d, r8d
0x180025760  lea     edx, [r9+8]
0x180025764  mov     rcx, [rcx]
0x180025767  call    cs:__imp_NetSetupGetObjects
0x18002576d  test    eax, eax
0x18002576f  jns     short loc_18002578A
0x180025771  mov     rcx, [rbp+30h]; this
0x180025775  mov     r9d, eax; char *
0x180025778  lea     r8, aOnecoreInterna; "onecore\\internal\\net\\inc\\netsetupcx"...
0x18002577f  mov     edx, 498h; void *
0x180025784  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002578a  mov     ecx, [rbp+arg_10]
0x18002578d  mov     [rbp+var_18], ecx
0x180025790  mov     rax, [rbp+arg_18]
0x180025794  mov     [rbp+var_10], rax
0x180025798  mov     qword ptr [rbx], 0
0x18002579f  mov     qword ptr [rbx+8], 0
0x1800257a7  mov     qword ptr [rbx+10h], 0
0x1800257af  mov     [rbp+var_28], 1
0x1800257b6  mov     edx, ecx
0x1800257b8  test    ecx, ecx
0x1800257ba  jz      short loc_1800257C7
0x1800257bc  mov     rcx, rbx
0x1800257bf  call    ?_Reallocate@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Reallocate(unsigned __int64)
0x1800257c4  mov     ecx, [rbp+arg_10]
0x1800257c7  xor     r14d, r14d
0x1800257ca  test    ecx, ecx
0x1800257cc  jz      loc_1800258A3
0x1800257d2  mov     ecx, 28h ; '('; Size
0x1800257d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800257dc  mov     rdi, rax
0x1800257df  mov     [rbp+arg_0], rax
0x1800257e3  test    rax, rax
0x1800257e6  jz      short loc_180025812
0x1800257e8  mov     r8d, r14d
0x1800257eb  shl     r8, 5
0x1800257ef  mov     rdx, [rbp+arg_18]
0x1800257f3  mov     ecx, [r8+rdx]
0x1800257f7  mov     [rax], r15
0x1800257fa  mov     qword ptr [rax+8], 0
0x180025802  mov     [rax+10h], ecx
0x180025805  movups  xmm0, xmmword ptr [r8+rdx+4]
0x18002580b  movdqu  xmmword ptr [rax+14h], xmm0
0x180025810  jmp     short loc_180025814
0x180025812  xor     edi, edi
0x180025814  mov     [rbp+var_20], rdi
0x180025818  mov     rax, [rbx+8]
0x18002581c  lea     rcx, [rbp+var_20]
0x180025820  cmp     rcx, rax
0x180025823  jnb     short loc_180025863
0x180025825  lea     rcx, [rbp+var_20]
0x180025829  cmp     [rbx], rcx
0x18002582c  ja      short loc_180025863
0x18002582e  lea     rdi, [rbp+var_20]
0x180025832  sub     rdi, [rbx]
0x180025835  sar     rdi, 3
0x180025839  cmp     rax, [rbx+10h]
0x18002583d  jnz     short loc_180025847
0x18002583f  mov     rcx, rbx
0x180025842  call    ?_Reserve@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Reserve(unsigned __int64)
0x180025847  mov     rdx, [rbx]
0x18002584a  mov     rcx, [rbx+8]
0x18002584e  mov     rax, [rdx+rdi*8]
0x180025852  mov     qword ptr [rdx+rdi*8], 0
0x18002585a  mov     [rcx], rax
0x18002585d  mov     rsi, [rbp+var_20]
0x180025861  jmp     short loc_18002587A
0x180025863  cmp     rax, [rbx+10h]
0x180025867  jnz     short loc_180025871
0x180025869  mov     rcx, rbx
0x18002586c  call    ?_Reserve@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Reserve(unsigned __int64)
0x180025871  xor     esi, esi
0x180025873  mov     rax, [rbx+8]
0x180025877  mov     [rax], rdi
0x18002587a  add     qword ptr [rbx+8], 8
0x18002587f  test    rsi, rsi
0x180025882  jz      short loc_180025896
0x180025884  lea     rcx, [rsi+8]
0x180025888  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002588d  mov     rcx, rsi
0x180025890  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025896  inc     r14d
0x180025899  cmp     r14d, [rbp+arg_10]
0x18002589d  jb      loc_1800257D2
0x1800258a3  lea     rcx, [rbp+var_18]; this
0x1800258a7  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x1800258ac  mov     rax, rbx
0x1800258af  add     rsp, 78h
0x1800258b3  pop     r15
0x1800258b5  pop     r14
0x1800258b7  pop     rdi
0x1800258b8  pop     rsi
0x1800258b9  pop     rbx
0x1800258ba  pop     rbp
0x1800258bb  retn
```
