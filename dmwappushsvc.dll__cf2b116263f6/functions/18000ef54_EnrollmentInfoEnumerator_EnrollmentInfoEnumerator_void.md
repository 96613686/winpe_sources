# EnrollmentInfoEnumerator::~EnrollmentInfoEnumerator(void)

- ea: `0x18000ef54`
- end: `0x18000efd1`
- name: `??1EnrollmentInfoEnumerator@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(EnrollmentInfoEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f680`

## callees

- `0x18000ef54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000efb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000efb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef96`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef96`

## pseudocode

```c
void __fastcall EnrollmentInfoEnumerator::~EnrollmentInfoEnumerator(EnrollmentInfoEnumerator *this)
{
  bool v1; // zf
  __int64 i; // rdi
  OLECHAR *v4; // rcx

  v1 = *((_QWORD *)this + 6) == 0;
  *(_QWORD *)this = &EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'};
  *((_QWORD *)this + 1) = &EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'};
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 10); i = (unsigned int)(i + 1) )
    {
      v4 = *(OLECHAR **)(*((_QWORD *)this + 6) + 8 * i);
      if ( v4 )
      {
        SysFreeString(v4);
        *(_QWORD *)(*((_QWORD *)this + 6) + 8 * i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x18000ef54  mov     [rsp+arg_0], rbx
0x18000ef59  mov     [rsp+arg_8], rsi
0x18000ef5e  push    rdi
0x18000ef5f  sub     rsp, 20h
0x18000ef63  cmp     qword ptr [rcx+30h], 0
0x18000ef68  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIEnrollmentInfoEnumerator@@@; const EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'}
0x18000ef6f  mov     [rcx], rax
0x18000ef72  mov     rbx, rcx
0x18000ef75  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIAttachEnrollEngine@@@; const EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'}
0x18000ef7c  mov     [rcx+8], rax
0x18000ef80  jz      short loc_18000EFC1
0x18000ef82  xor     edi, edi
0x18000ef84  cmp     [rcx+28h], edi
0x18000ef87  jbe     short loc_18000EFAF
0x18000ef89  mov     rax, [rbx+30h]
0x18000ef8d  mov     rcx, [rax+rdi*8]; bstrString
0x18000ef91  test    rcx, rcx
0x18000ef94  jz      short loc_18000EFA8
0x18000ef96  call    cs:__imp_SysFreeString
0x18000ef9c  mov     rax, [rbx+30h]
0x18000efa0  mov     qword ptr [rax+rdi*8], 0
0x18000efa8  inc     edi
0x18000efaa  cmp     edi, [rbx+28h]
0x18000efad  jb      short loc_18000EF89
0x18000efaf  mov     rcx, [rbx+30h]; pv
0x18000efb3  call    cs:__imp_CoTaskMemFree
0x18000efb9  mov     qword ptr [rbx+30h], 0
0x18000efc1  mov     rbx, [rsp+28h+arg_0]
0x18000efc6  mov     rsi, [rsp+28h+arg_8]
0x18000efcb  add     rsp, 20h
0x18000efcf  pop     rdi
0x18000efd0  retn
```
