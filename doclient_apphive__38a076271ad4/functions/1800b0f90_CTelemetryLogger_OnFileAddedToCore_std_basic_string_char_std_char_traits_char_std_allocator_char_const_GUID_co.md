# CTelemetryLogger::OnFileAddedToCore(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,_GUID const &)

- ea: `0x1800b0f90`
- end: `0x1800b109a`
- name: `?OnFileAddedToCore@CTelemetryLogger@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU_GUID@@@Z`
- size: `266`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002cff4`
- `0x18006de00`
- `0x18009d138`
- `0x1800bafa8`

## callees

- `0x180008fb8`
- `0x18004c614`
- `0x1800b0f90`
- `0x1800b9274`
- `0x1800f82f0`
- `0x1801099b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1072`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1072`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b0fcd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b0fcd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b1024`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b1024`

## string_xrefs

- `0x1800b1032`: `CoCreateGuid failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTelemetryLogger::OnFileAddedToCore(RTL_SRWLOCK *a1, __int64 a2, GUID *a3)
{
  RTL_SRWLOCK *v6; // rbx
  GUID v7; // xmm6
  unsigned int v8; // eax
  const char *v9; // [rsp+28h] [rbp-60h]
  GUID Buf1; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v6 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  *(_QWORD *)&Buf1.Data1 = 0;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
    a1,
    &Buf1,
    a2);
  if ( *(PVOID *)&Buf1.Data1 == a1->Ptr )
  {
    v7 = *a3;
    Buf1 = *a3;
    if ( !memcmp(&Buf1, &GUID_NULL, 0x10u) )
    {
      v8 = CoCreateGuid(&Buf1);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x84,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\TelemetryLogger.cpp",
        (const char *)v8,
        (int)"CoCreateGuid failed",
        v9);
      v7 = Buf1;
    }
    *(GUID *)(std::map<std::string,CTelemetryLogger::FileInfo>::operator[](a1, a2) + 48) = v7;
  }
  else
  {
    ++*(_DWORD *)(*(_QWORD *)&Buf1.Data1 + 148LL);
  }
  ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x1800b0f90  mov     [rsp+arg_18], rbx
0x1800b0f95  push    rbp
0x1800b0f96  push    rsi
0x1800b0f97  push    rdi
0x1800b0f98  sub     rsp, 70h
0x1800b0f9c  movaps  [rsp+88h+var_28], xmm6
0x1800b0fa1  mov     rax, cs:__security_cookie
0x1800b0fa8  xor     rax, rsp
0x1800b0fab  mov     [rsp+88h+var_38], rax
0x1800b0fb0  mov     rbp, r8
0x1800b0fb3  mov     rsi, rdx
0x1800b0fb6  mov     rdi, rcx
0x1800b0fb9  xorps   xmm0, xmm0
0x1800b0fbc  movups  [rsp+88h+var_58], xmm0
0x1800b0fc1  lea     rbx, [rcx+10h]
0x1800b0fc5  mov     qword ptr [rsp+88h+var_58], rbx
0x1800b0fca  mov     rcx, rbx; SRWLock
0x1800b0fcd  call    cs:__imp_AcquireSRWLockExclusive
0x1800b0fd3  mov     byte ptr [rsp+88h+var_58+8], 1
0x1800b0fd8  mov     qword ptr [rsp+88h+Buf1], 0
0x1800b0fe1  mov     r8, rsi
0x1800b0fe4  lea     rdx, [rsp+88h+Buf1]
0x1800b0fe9  mov     rcx, rdi
0x1800b0fec  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x1800b0ff1  mov     rax, qword ptr [rsp+88h+Buf1]
0x1800b0ff6  cmp     rax, [rdi]
0x1800b0ff9  jnz     short loc_1800B1069
0x1800b0ffb  movups  xmm6, xmmword ptr [rbp+0]
0x1800b0fff  movups  [rsp+88h+Buf1], xmm6
0x1800b1004  mov     r8d, 10h; Size
0x1800b100a  lea     rdx, GUID_NULL; Buf2
0x1800b1011  lea     rcx, [rsp+88h+Buf1]; Buf1
0x1800b1016  call    memcmp
0x1800b101b  test    eax, eax
0x1800b101d  jnz     short loc_1800B1057
0x1800b101f  lea     rcx, [rsp+88h+Buf1]; pguid
0x1800b1024  call    cs:__imp_CoCreateGuid
0x1800b102a  mov     rcx, [rsp+88h]; this
0x1800b1032  lea     rdx, aCocreateguidFa; "CoCreateGuid failed"
0x1800b1039  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1800b103e  mov     r9d, eax; char *
0x1800b1041  lea     r8, aCW1SSrcDeliver_104; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800b1048  mov     edx, 84h; void *
0x1800b104d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800b1052  movups  xmm6, [rsp+88h+Buf1]
0x1800b1057  mov     rdx, rsi
0x1800b105a  mov     rcx, rdi
0x1800b105d  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UFileInfo@CTelemetryLogger@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UFileInfo@CTelemetryLogger@@@std@@@2@@std@@QEAAAEAUFileInfo@CTelemetryLogger@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,CTelemetryLogger::FileInfo>::operator[](std::string const &)
0x1800b1062  movdqu  xmmword ptr [rax+30h], xmm6
0x1800b1067  jmp     short loc_1800B106F
0x1800b1069  inc     dword ptr [rax+94h]
0x1800b106f  mov     rcx, rbx; SRWLock
0x1800b1072  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b1078  mov     rcx, [rsp+88h+var_38]
0x1800b107d  xor     rcx, rsp; StackCookie
0x1800b1080  call    __security_check_cookie
0x1800b1085  mov     rbx, [rsp+88h+arg_18]
0x1800b108d  movaps  xmm6, [rsp+88h+var_28]
0x1800b1092  add     rsp, 70h
0x1800b1096  pop     rdi
0x1800b1097  pop     rsi
0x1800b1098  pop     rbp
0x1800b1099  retn
```
