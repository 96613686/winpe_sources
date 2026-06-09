# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x18002af2c`
- end: `0x18002b0f9`
- name: `??$GetAllObjectsInner@VNetworkInterface@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `461`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002bc88`
- `0x18002bd2c`

## callees

- `0x180001274`
- `0x1800215a4`
- `0x180025e0c`
- `0x180026c18`
- `0x180026f34`
- `0x180027064`
- `0x18002af2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b0cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b0cc`
- `NetSetupApi!NetSetupGetObjects` at `0x18002afa3`
- `NetSetupApi!NetSetupGetObjects` at `0x18002afa3`

## pseudocode

```c
_QWORD *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(
        _QWORD *a1,
        _QWORD *a2)
{
  int Objects; // eax
  int v5; // [rsp+60h] [rbp-18h] BYREF
  __int64 v6; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  Objects = NetSetupGetObjects(*a1, 2, 0);
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
0x18002af2c  mov     r11, rsp
0x18002af2f  mov     [r11+20h], r9
0x18002af33  mov     [r11+18h], r8d
0x18002af37  mov     [r11+10h], rdx
0x18002af3b  push    rbp
0x18002af3c  push    rbx
0x18002af3d  push    rsi
0x18002af3e  push    rdi
0x18002af3f  push    r14
0x18002af41  push    r15
0x18002af43  mov     rbp, rsp
0x18002af46  sub     rsp, 78h
0x18002af4a  mov     rbx, rdx
0x18002af4d  mov     r15, rcx
0x18002af50  mov     [rbp+var_28], 0
0x18002af57  mov     [rbp+arg_10], 0
0x18002af5e  mov     [rbp+arg_18], 0
0x18002af66  lea     rax, [rbp+arg_18]
0x18002af6a  mov     [r11-60h], rax
0x18002af6e  lea     rax, [rbp+arg_10]
0x18002af72  mov     [r11-68h], rax
0x18002af76  mov     rax, [rbp+arg_28]
0x18002af7a  mov     [r11-70h], rax
0x18002af7e  mov     [rsp+78h+var_48], 1
0x18002af86  mov     qword ptr [r11-80h], 0
0x18002af8e  mov     [rsp+78h+var_58], 0; int
0x18002af96  xor     r9d, r9d
0x18002af99  xor     r8d, r8d
0x18002af9c  lea     edx, [r9+2]
0x18002afa0  mov     rcx, [rcx]
0x18002afa3  call    cs:__imp_NetSetupGetObjects
0x18002afa9  test    eax, eax
0x18002afab  jns     short loc_18002AFC6
0x18002afad  mov     rcx, [rbp+30h]; this
0x18002afb1  mov     r9d, eax; char *
0x18002afb4  lea     r8, aOnecoreInterna; "onecore\\internal\\net\\inc\\netsetupcx"...
0x18002afbb  mov     edx, 498h; void *
0x18002afc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002afc6  mov     ecx, [rbp+arg_10]
0x18002afc9  mov     [rbp+var_18], ecx
0x18002afcc  mov     rax, [rbp+arg_18]
0x18002afd0  mov     [rbp+var_10], rax
0x18002afd4  mov     qword ptr [rbx], 0
0x18002afdb  mov     qword ptr [rbx+8], 0
0x18002afe3  mov     qword ptr [rbx+10h], 0
0x18002afeb  mov     [rbp+var_28], 1
0x18002aff2  mov     edx, ecx
0x18002aff4  test    ecx, ecx
0x18002aff6  jz      short loc_18002B003
0x18002aff8  mov     rcx, rbx
0x18002affb  call    ?_Reallocate@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Reallocate(unsigned __int64)
0x18002b000  mov     ecx, [rbp+arg_10]
0x18002b003  xor     r14d, r14d
0x18002b006  test    ecx, ecx
0x18002b008  jz      loc_18002B0DF
0x18002b00e  mov     ecx, 28h ; '('; Size
0x18002b013  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b018  mov     rdi, rax
0x18002b01b  mov     [rbp+arg_0], rax
0x18002b01f  test    rax, rax
0x18002b022  jz      short loc_18002B04E
0x18002b024  mov     r8d, r14d
0x18002b027  shl     r8, 5
0x18002b02b  mov     rdx, [rbp+arg_18]
0x18002b02f  mov     ecx, [r8+rdx]
0x18002b033  mov     [rax], r15
0x18002b036  mov     qword ptr [rax+8], 0
0x18002b03e  mov     [rax+10h], ecx
0x18002b041  movups  xmm0, xmmword ptr [r8+rdx+4]
0x18002b047  movdqu  xmmword ptr [rax+14h], xmm0
0x18002b04c  jmp     short loc_18002B050
0x18002b04e  xor     edi, edi
0x18002b050  mov     [rbp+var_20], rdi
0x18002b054  mov     rax, [rbx+8]
0x18002b058  lea     rcx, [rbp+var_20]
0x18002b05c  cmp     rcx, rax
0x18002b05f  jnb     short loc_18002B09F
0x18002b061  lea     rcx, [rbp+var_20]
0x18002b065  cmp     [rbx], rcx
0x18002b068  ja      short loc_18002B09F
0x18002b06a  lea     rdi, [rbp+var_20]
0x18002b06e  sub     rdi, [rbx]
0x18002b071  sar     rdi, 3
0x18002b075  cmp     rax, [rbx+10h]
0x18002b079  jnz     short loc_18002B083
0x18002b07b  mov     rcx, rbx
0x18002b07e  call    ?_Reserve@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Reserve(unsigned __int64)
0x18002b083  mov     rdx, [rbx]
0x18002b086  mov     rcx, [rbx+8]
0x18002b08a  mov     rax, [rdx+rdi*8]
0x18002b08e  mov     qword ptr [rdx+rdi*8], 0
0x18002b096  mov     [rcx], rax
0x18002b099  mov     rsi, [rbp+var_20]
0x18002b09d  jmp     short loc_18002B0B6
0x18002b09f  cmp     rax, [rbx+10h]
0x18002b0a3  jnz     short loc_18002B0AD
0x18002b0a5  mov     rcx, rbx
0x18002b0a8  call    ?_Reserve@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Reserve(unsigned __int64)
0x18002b0ad  xor     esi, esi
0x18002b0af  mov     rax, [rbx+8]
0x18002b0b3  mov     [rax], rdi
0x18002b0b6  add     qword ptr [rbx+8], 8
0x18002b0bb  test    rsi, rsi
0x18002b0be  jz      short loc_18002B0D2
0x18002b0c0  lea     rcx, [rsi+8]
0x18002b0c4  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002b0c9  mov     rcx, rsi
0x18002b0cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b0d2  inc     r14d
0x18002b0d5  cmp     r14d, [rbp+arg_10]
0x18002b0d9  jb      loc_18002B00E
0x18002b0df  lea     rcx, [rbp+var_18]; this
0x18002b0e3  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x18002b0e8  mov     rax, rbx
0x18002b0eb  add     rsp, 78h
0x18002b0ef  pop     r15
0x18002b0f1  pop     r14
0x18002b0f3  pop     rdi
0x18002b0f4  pop     rsi
0x18002b0f5  pop     rbx
0x18002b0f6  pop     rbp
0x18002b0f7  retn
```
