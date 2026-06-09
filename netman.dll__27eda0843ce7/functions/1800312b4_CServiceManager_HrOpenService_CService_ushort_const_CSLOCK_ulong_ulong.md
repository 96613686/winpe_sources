# CServiceManager::HrOpenService(CService *,ushort const *,CSLOCK,ulong,ulong)

- ea: `0x1800312b4`
- end: `0x180031320`
- name: `?HrOpenService@CServiceManager@@QEAAJPEAVCService@@PEBGW4CSLOCK@@KK@Z`
- size: `108`
- prototype: `int __high(struct CService *, const unsigned __int16 *, enum CSLOCK, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180031328`

## callees

- `0x18003060c`
- `0x18003123c`
- `0x180031268`
- `0x1800312b4`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x1800312f9`
- `ADVAPI32!OpenServiceW` at `0x1800312f9`

## string_xrefs

- `0x1800312ec`: `RemoteAccess`

## pseudocode

```c
__int64 __fastcall CServiceManager::HrOpenService(SC_HANDLE *a1, CService *a2)
{
  unsigned int v2; // ebx
  SC_HANDLE v5; // rax

  v2 = 0;
  if ( *a1 || (v2 = CServiceManager::HrOpen(a1)) == 0 )
  {
    if ( *(_QWORD *)a2 )
      CService::Close(a2);
    v5 = OpenServiceW(*a1, L"RemoteAccess", 4u);
    *(_QWORD *)a2 = v5;
    if ( !v5 )
      return (unsigned int)HrFromLastWin32Error();
  }
  return v2;
}

```

## disassembly

```asm
0x1800312b4  mov     [rsp+arg_0], rbx
0x1800312b9  mov     [rsp+arg_8], rsi
0x1800312be  push    rdi
0x1800312bf  sub     rsp, 30h
0x1800312c3  xor     ebx, ebx
0x1800312c5  mov     rdi, rdx
0x1800312c8  mov     rsi, rcx
0x1800312cb  cmp     [rcx], rbx
0x1800312ce  jnz     short loc_1800312DB
0x1800312d0  call    ?HrOpen@CServiceManager@@QEAAJW4CSLOCK@@KPEBG1@Z; CServiceManager::HrOpen(CSLOCK,ulong,ushort const *,ushort const *)
0x1800312d5  mov     ebx, eax
0x1800312d7  test    eax, eax
0x1800312d9  jnz     short loc_18003130E
0x1800312db  cmp     qword ptr [rdi], 0
0x1800312df  jz      short loc_1800312E9
0x1800312e1  mov     rcx, rdi; this
0x1800312e4  call    ?Close@CService@@QEAAXXZ; CService::Close(void)
0x1800312e9  mov     rcx, [rsi]; hSCManager
0x1800312ec  lea     rdx, ?c_szSvcRemoteAccess@@3QBGB; "RemoteAccess"
0x1800312f3  mov     r8d, 4; dwDesiredAccess
0x1800312f9  call    cs:__imp_OpenServiceW
0x1800312ff  mov     [rdi], rax
0x180031302  test    rax, rax
0x180031305  jnz     short loc_18003130E
0x180031307  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18003130c  mov     ebx, eax
0x18003130e  mov     rsi, [rsp+38h+arg_8]
0x180031313  mov     eax, ebx
0x180031315  mov     rbx, [rsp+38h+arg_0]
0x18003131a  add     rsp, 30h
0x18003131e  pop     rdi
0x18003131f  retn
```
