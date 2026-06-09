# CQueueManager::RemoveUntriggeredQueues(void)

- ea: `0x14000456c`
- end: `0x140004640`
- name: `?RemoveUntriggeredQueues@CQueueManager@@QEAAXXZ`
- size: `212`
- prototype: `void __fastcall(CQueueManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000afa0`

## callees

- `0x14000190c`
- `0x140003d28`
- `0x14000456c`
- `0x140004e90`
- `0x1400053dc`
- `0x1400060b0`
- `0x1400060f4`
- `0x140006418`
- `0x14001ca70`

## pseudocode

```c
void __fastcall CQueueManager::RemoveUntriggeredQueues(CQueueManager *this)
{
  __int64 v2; // rbx
  CQueue *v3; // rsi
  __int64 i; // rax
  CReadWriteLock *v5; // [rsp+40h] [rbp+8h] BYREF
  char v6; // [rsp+48h] [rbp+10h] BYREF

  v5 = (CQueueManager *)((char *)this + 16);
  CReadWriteLock::LockWrite((CQueueManager *)((char *)this + 16));
  v2 = **((_QWORD **)this + 6);
  while ( v2 != *((_QWORD *)this + 6) )
  {
    v3 = *(CQueue **)(v2 + 64);
    if ( CQueue::IsTriggerExist(v3) )
    {
      if ( *(_BYTE *)(v2 + 73) )
        invalid_parameter(0, 0, 0, 0, 0);
      if ( *(_BYTE *)(*(_QWORD *)(v2 + 16) + 73LL) )
      {
        for ( i = *(_QWORD *)(v2 + 8); !*(_BYTE *)(i + 73) && v2 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v2 = i;
      }
      else
      {
        i = std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::_Min();
      }
      v2 = i;
    }
    else
    {
      CQueue::CancelIoOperation(v3);
      CQueue::CloseQueueHandle(v3);
      v2 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::erase(
                        (char *)this + 40,
                        &v6,
                        v2);
    }
  }
  CSW::~CSW(&v5);
}

```

## disassembly

```asm
0x14000456c  mov     [rsp+arg_10], rbx
0x140004571  mov     [rsp+arg_18], rsi
0x140004576  push    rdi
0x140004577  sub     rsp, 30h
0x14000457b  mov     rdi, rcx
0x14000457e  add     rcx, 10h; this
0x140004582  mov     [rsp+38h+arg_0], rcx
0x140004587  call    ?LockWrite@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockWrite(void)
0x14000458c  nop
0x14000458d  mov     rbx, [rdi+30h]
0x140004591  mov     rbx, [rbx]
0x140004594  cmp     rbx, [rdi+30h]
0x140004598  jz      loc_140004626
0x14000459e  mov     rsi, [rbx+40h]
0x1400045a2  mov     rcx, rsi; this
0x1400045a5  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x1400045aa  test    al, al
0x1400045ac  jz      short loc_1400045FD
0x1400045ae  cmp     byte ptr [rbx+49h], 0
0x1400045b2  jz      short loc_1400045CE
0x1400045b4  mov     [rsp+38h+Reserved], 0; Reserved
0x1400045bd  xor     r9d, r9d; LineNo
0x1400045c0  xor     r8d, r8d; FileName
0x1400045c3  xor     edx, edx; FunctionName
0x1400045c5  xor     ecx, ecx; Expression
0x1400045c7  call    _invalid_parameter
0x1400045cc  jmp     short loc_140004594
0x1400045ce  mov     rcx, [rbx+10h]
0x1400045d2  cmp     byte ptr [rcx+49h], 0
0x1400045d6  jnz     short loc_1400045DF
0x1400045d8  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@@std@@@2@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::_Node *)
0x1400045dd  jmp     short loc_1400045F8
0x1400045df  mov     rax, [rbx+8]
0x1400045e3  jmp     short loc_1400045F2
0x1400045e5  cmp     rbx, [rax+10h]
0x1400045e9  jnz     short loc_1400045F8
0x1400045eb  mov     rbx, rax
0x1400045ee  mov     rax, [rax+8]
0x1400045f2  cmp     byte ptr [rax+49h], 0
0x1400045f6  jz      short loc_1400045E5
0x1400045f8  mov     rbx, rax
0x1400045fb  jmp     short loc_140004594
0x1400045fd  mov     rcx, rsi; this
0x140004600  call    ?CancelIoOperation@CQueue@@QEAAXXZ; CQueue::CancelIoOperation(void)
0x140004605  mov     rcx, rsi; this
0x140004608  call    ?CloseQueueHandle@CQueue@@QEAAXXZ; CQueue::CloseQueueHandle(void)
0x14000460d  lea     rcx, [rdi+28h]
0x140004611  mov     r8, rbx
0x140004614  lea     rdx, [rsp+38h+arg_8]
0x140004619  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::erase(std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::iterator)
0x14000461e  mov     rbx, [rax]
0x140004621  jmp     loc_140004594
0x140004626  lea     rcx, [rsp+38h+arg_0]; this
0x14000462b  call    ??1CSW@@QEAA@XZ; CSW::~CSW(void)
0x140004630  mov     rbx, [rsp+38h+arg_10]
0x140004635  mov     rsi, [rsp+38h+arg_18]
0x14000463a  add     rsp, 30h
0x14000463e  pop     rdi
0x14000463f  retn
```
