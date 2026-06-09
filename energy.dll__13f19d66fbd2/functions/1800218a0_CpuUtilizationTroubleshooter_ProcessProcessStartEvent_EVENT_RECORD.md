# CpuUtilizationTroubleshooter::ProcessProcessStartEvent(_EVENT_RECORD *)

- ea: `0x1800218a0`
- end: `0x180021a81`
- name: `?ProcessProcessStartEvent@CpuUtilizationTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `481`
- prototype: `void(CpuUtilizationTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180019d60`

## callees

- `0x18000ae78`
- `0x18000aed4`
- `0x18000b6f0`
- `0x18001be60`
- `0x180020b14`
- `0x1800218a0`
- `0x180021a88`
- `0x180021e00`
- `0x180021f2c`
- `0x18003bb60`
- `0x18003bf74`
- `0x18003bf8c`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18002193a`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18002193a`

## string_xrefs

- `0x180021904`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CpuUtilizationTroubleshooter::ProcessProcessStartEvent(
        CpuUtilizationTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  unsigned int v4; // ebx
  __int128 *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // ebx
  BYTE pBuffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h]
  __int64 v12; // [rsp+60h] [rbp-A0h]
  __int128 v13; // [rsp+68h] [rbp-98h] BYREF
  __int64 v14; // [rsp+78h] [rbp-88h]
  unsigned __int64 v15; // [rsp+80h] [rbp-80h]
  _BYTE v16[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v18[40]; // [rsp+D8h] [rbp-28h] BYREF

  *(_DWORD *)pBuffer = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  std::wstring::_Construct_empty(&v13);
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ProcessId";
  if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, pBuffer) && !(unsigned int)GetEventProperty(a2) )
  {
    v4 = *(_DWORD *)pBuffer;
    pPropertyData = 0;
    v11 = 0;
    v12 = 0;
    v5 = &v13;
    if ( v15 > 7 )
      v5 = (__int128 *)v13;
    std::wstring::_Construct<2,unsigned short const *>(&pPropertyData, v5, v14);
    v6 = Process::Process(v16, &pPropertyData, v4, (char *)this + 144);
    v7 = *((_QWORD *)this + 7);
    if ( v7 == *((_QWORD *)this + 8) )
    {
      std::vector<Process>::_Emplace_reallocate<Process>((char *)this + 48, *((_QWORD *)this + 7), v6);
    }
    else
    {
      Process::Process(v7, v6);
      *((_QWORD *)this + 7) += 104LL;
    }
    std::vector<ImageMapping>::_Tidy(v18);
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned __int64>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<unsigned long const,unsigned __int64>,void *>>>(
      v17,
      v17);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v16);
    v8 = -991146299 * ((__int64)(*((_QWORD *)this + 7) - *((_QWORD *)this + 6)) >> 3) - 1;
    *(_DWORD *)(*(_QWORD *)std::map<unsigned long,unsigned long>::_Try_emplace<unsigned long const &,>(
                             (char *)this + 72,
                             &pPropertyData,
                             pBuffer)
              + 32LL) = v8;
    *((_DWORD *)this + 66) |= 0x20u;
  }
  if ( v15 > 7 )
    std::_Deallocate<16>((void *)v13, 2 * v15 + 2);
}

```

## disassembly

```asm
0x1800218a0  mov     [rsp-8+arg_10], rbx
0x1800218a5  push    rbp
0x1800218a6  push    rsi
0x1800218a7  push    rdi
0x1800218a8  lea     rbp, [rsp-10h]
0x1800218ad  sub     rsp, 110h
0x1800218b4  mov     rax, cs:__security_cookie
0x1800218bb  xor     rax, rsp
0x1800218be  mov     [rbp+20h+var_20], rax
0x1800218c2  mov     rbx, rdx
0x1800218c5  mov     rsi, rcx
0x1800218c8  mov     dword ptr [rsp+120h+var_E0], 0
0x1800218d0  xorps   xmm0, xmm0
0x1800218d3  movups  [rsp+120h+var_B8], xmm0
0x1800218d8  mov     [rsp+120h+var_A8], 0
0x1800218e1  mov     [rbp+20h+var_A0], 0
0x1800218e9  lea     rcx, [rsp+120h+var_B8]
0x1800218ee  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800218f3  nop
0x1800218f4  mov     [rsp+120h+var_D8.Reserved], 0
0x1800218fc  mov     [rsp+120h+var_D8.ArrayIndex], 0FFFFFFFFh
0x180021904  lea     rax, aProcessid; "ProcessId"
0x18002190b  mov     [rsp+120h+var_D8.PropertyName], rax
0x180021910  lea     rax, [rsp+120h+var_E0]
0x180021915  mov     [rsp+120h+pBuffer], rax; pBuffer
0x18002191a  mov     [rsp+120h+BufferSize], 4; BufferSize
0x180021922  lea     rax, [rsp+120h+var_D8]
0x180021927  mov     [rsp+120h+pPropertyData], rax; pPropertyData
0x18002192c  mov     r9d, 1; PropertyDataCount
0x180021932  xor     r8d, r8d; pTdhContext
0x180021935  xor     edx, edx; TdhContextCount
0x180021937  mov     rcx, rbx; pEvent
0x18002193a  call    cs:__imp_TdhGetProperty
0x180021940  test    eax, eax
0x180021942  jnz     short loc_18002195F
0x180021944  mov     r9b, 1
0x180021947  lea     r8, [rsp+120h+var_B8]
0x18002194c  lea     rdx, aImagefilename; "ImageFileName"
0x180021953  mov     rcx, rbx; pEvent
0x180021956  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18002195b  test    eax, eax
0x18002195d  jz      short loc_18002198C
0x18002195f  mov     rdx, [rbp+20h+var_A0]
0x180021963  cmp     rdx, 7
0x180021967  ja      loc_180021A6A
0x18002196d  mov     rcx, [rbp+20h+var_20]
0x180021971  xor     rcx, rsp; StackCookie
0x180021974  call    __security_check_cookie
0x180021979  mov     rbx, [rsp+120h+arg_10]
0x180021981  add     rsp, 110h
0x180021988  pop     rdi
0x180021989  pop     rsi
0x18002198a  pop     rbp
0x18002198b  retn
0x18002198c  mov     ebx, dword ptr [rsp+120h+var_E0]
0x180021990  xorps   xmm0, xmm0
0x180021993  movups  xmmword ptr [rsp+120h+var_D8.PropertyName], xmm0
0x180021998  mov     [rsp+120h+var_C8], 0
0x1800219a1  mov     [rsp+120h+var_C0], 0
0x1800219aa  lea     rdx, [rsp+120h+var_B8]
0x1800219af  cmp     [rbp+20h+var_A0], 7
0x1800219b4  cmova   rdx, qword ptr [rsp+120h+var_B8]
0x1800219ba  mov     r8, [rsp+120h+var_A8]
0x1800219bf  lea     rcx, [rsp+120h+var_D8]
0x1800219c4  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800219c9  lea     r9, [rsi+90h]
0x1800219d0  mov     r8d, ebx
0x1800219d3  lea     rdx, [rsp+120h+var_D8]
0x1800219d8  lea     rcx, [rbp+20h+var_90]
0x1800219dc  call    ??0Process@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAV?$vector@VImageMapping@@V?$allocator@VImageMapping@@@std@@@2@@Z; Process::Process(std::wstring,ulong,std::vector<ImageMapping> *)
0x1800219e1  nop
0x1800219e2  mov     rcx, [rsi+38h]
0x1800219e6  cmp     rcx, [rsi+40h]
0x1800219ea  jz      short loc_180021A59
0x1800219ec  mov     rdx, rax
0x1800219ef  call    ??0Process@@QEAA@$$QEAV0@@Z; Process::Process(Process &&)
0x1800219f4  add     qword ptr [rsi+38h], 68h ; 'h'
0x1800219f9  lea     rcx, [rbp+20h+var_48]
0x1800219fd  call    ?_Tidy@?$vector@VImageMapping@@V?$allocator@VImageMapping@@@std@@@std@@AEAAXXZ; std::vector<ImageMapping>::_Tidy(void)
0x180021a02  lea     rdx, [rbp+20h+var_58]
0x180021a06  lea     rcx, [rbp+20h+var_58]
0x180021a0a  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBK_K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBK_K@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,unsigned __int64>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<ulong const,unsigned __int64>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,unsigned __int64>,void *>> &)
0x180021a0f  lea     rcx, [rbp+20h+var_90]; void *
0x180021a13  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180021a18  mov     rbx, [rsi+38h]
0x180021a1c  sub     rbx, [rsi+30h]
0x180021a20  sar     rbx, 3
0x180021a24  mov     rcx, 4EC4EC4EC4EC4EC5h
0x180021a2e  imul    rbx, rcx
0x180021a32  dec     ebx
0x180021a34  lea     rcx, [rsi+48h]
0x180021a38  lea     r8, [rsp+120h+var_E0]
0x180021a3d  lea     rdx, [rsp+120h+var_D8]
0x180021a42  call    ??$_Try_emplace@AEBK$$V@?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKK@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,ulong>::_Try_emplace<ulong const &,>(ulong const &)
0x180021a47  mov     rcx, [rax]
0x180021a4a  mov     [rcx+20h], ebx
0x180021a4d  or      dword ptr [rsi+108h], 20h
0x180021a54  jmp     loc_18002195F
0x180021a59  mov     r8, rax
0x180021a5c  mov     rdx, rcx
0x180021a5f  lea     rcx, [rsi+30h]
0x180021a63  call    ??$_Emplace_reallocate@VProcess@@@?$vector@VProcess@@V?$allocator@VProcess@@@std@@@std@@AEAAPEAVProcess@@QEAV2@$$QEAV2@@Z; std::vector<Process>::_Emplace_reallocate<Process>(Process * const,Process &&)
0x180021a68  jmp     short loc_1800219F9
0x180021a6a  lea     rdx, ds:2[rdx*2]
0x180021a72  mov     rcx, qword ptr [rsp+120h+var_B8]
0x180021a77  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021a7c  jmp     loc_18002196D
```
