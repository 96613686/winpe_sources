# NTCache::clear(void)

- ea: `0x18001dc78`
- end: `0x18001dd1f`
- name: `?clear@NTCache@@QEAAXXZ`
- size: `167`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001da78`
- `0x18001dc4c`

## callees

- `0x180017f3c`
- `0x1800181ec`
- `0x18001dc78`
- `0x18001f5d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001dd18`
- `KERNEL32!EnterCriticalSection` at `0x18001dcab`
- `KERNEL32!EnterCriticalSection` at `0x18001dcab`
- `KERNEL32!TryEnterCriticalSection` at `0x18001dc8f`
- `KERNEL32!TryEnterCriticalSection` at `0x18001dc8f`
- `KERNEL32!SwitchToThread` at `0x18001dca0`
- `KERNEL32!SwitchToThread` at `0x18001dca0`

## pseudocode

```c
void __fastcall NTCache::clear(LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // ebx
  __int64 *v3; // rbx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 *LockSemaphore; // [rsp+28h] [rbp-20h]
  __int64 *v6; // [rsp+30h] [rbp-18h]

  v2 = 0;
  while ( !TryEnterCriticalSection(lpCriticalSection) )
  {
    if ( ++v2 >= 100 )
    {
      EnterCriticalSection(lpCriticalSection);
      break;
    }
    SwitchToThread();
  }
  LockSemaphore = (__int64 *)lpCriticalSection[1].LockSemaphore;
  v4 = *LockSemaphore;
  v6 = &LockSemaphore[(__int64)lpCriticalSection[1].DebugInfo];
  while ( 1 )
  {
    hash_table<unsigned long,identity<unsigned long>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<unsigned long>>::const_iterator::find_node(&v4);
    if ( LockSemaphore == v6 )
      break;
    v3 = (__int64 *)v4;
    NTDomain::Release(*(NTDomain **)(v4 + 8));
    v4 = *v3;
  }
  hash_table<unsigned long,identity<unsigned long>,std::pair<unsigned long const,enum IASTYPEENUM>,ExtractFirst<std::pair<unsigned long const,enum IASTYPEENUM>>,std::equal_to<unsigned long>>::clear(&lpCriticalSection[1]);
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001dc78  mov     [rsp+arg_0], rbx
0x18001dc7d  mov     [rsp+arg_8], rsi
0x18001dc82  push    rdi
0x18001dc83  sub     rsp, 40h
0x18001dc87  mov     rdi, rcx
0x18001dc8a  xor     ebx, ebx
0x18001dc8c  mov     rcx, rdi; lpCriticalSection
0x18001dc8f  call    cs:__imp_TryEnterCriticalSection
0x18001dc95  test    eax, eax
0x18001dc97  jnz     short loc_18001DCB1
0x18001dc99  inc     ebx
0x18001dc9b  cmp     ebx, 64h ; 'd'
0x18001dc9e  jge     short loc_18001DCA8
0x18001dca0  call    cs:__imp_SwitchToThread
0x18001dca6  jmp     short loc_18001DC8C
0x18001dca8  mov     rcx, rdi; lpCriticalSection
0x18001dcab  call    cs:__imp_EnterCriticalSection
0x18001dcb1  mov     rcx, [rdi+40h]
0x18001dcb5  mov     [rsp+48h+var_20], rcx
0x18001dcba  mov     rax, [rcx]
0x18001dcbd  mov     [rsp+48h+var_28], rax
0x18001dcc2  mov     rax, [rdi+28h]
0x18001dcc6  lea     rcx, [rcx+rax*8]
0x18001dcca  mov     [rsp+48h+var_18], rcx
0x18001dccf  lea     rcx, [rsp+48h+var_28]
0x18001dcd4  call    ?find_node@const_iterator@?$hash_table@KU?$identity@K@@U?$pair@PEAVEAPSession@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KPEAVEAPSession@@@std@@@std@@@std@@@std@@@std@@UExtractor@EAPSessionTable@@U?$equal_to@K@3@@@IEAAXXZ; hash_table<ulong,identity<ulong>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<ulong>>::const_iterator::find_node(void)
0x18001dcd9  mov     rax, [rsp+48h+var_18]
0x18001dcde  cmp     [rsp+48h+var_20], rax
0x18001dce3  jz      short loc_18001DCFD
0x18001dce5  mov     rbx, [rsp+48h+var_28]
0x18001dcea  mov     rcx, [rbx+8]; this
0x18001dcee  call    ?Release@NTDomain@@QEAAXXZ; NTDomain::Release(void)
0x18001dcf3  mov     rax, [rbx]
0x18001dcf6  mov     [rsp+48h+var_28], rax
0x18001dcfb  jmp     short loc_18001DCCF
0x18001dcfd  lea     rcx, [rdi+28h]
0x18001dd01  call    ?clear@?$hash_table@KU?$identity@K@@U?$pair@$$CBKW4IASTYPEENUM@@@std@@V?$ExtractFirst@U?$pair@$$CBKW4IASTYPEENUM@@@std@@@@U?$equal_to@K@3@@@QEAAXXZ; hash_table<ulong,identity<ulong>,std::pair<ulong const,IASTYPEENUM>,ExtractFirst<std::pair<ulong const,IASTYPEENUM>>,std::equal_to<ulong>>::clear(void)
0x18001dd06  mov     rcx, rdi
0x18001dd09  mov     rbx, [rsp+48h+arg_0]
0x18001dd0e  mov     rsi, [rsp+48h+arg_8]
0x18001dd13  add     rsp, 40h
0x18001dd17  pop     rdi
0x18001dd18  jmp     cs:__imp_LeaveCriticalSection
```
