# EnrollmentInfoEnumerator::~EnrollmentInfoEnumerator(void)

- ea: `0x18003d78c`
- end: `0x18003d816`
- name: `??1EnrollmentInfoEnumerator@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(EnrollmentInfoEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dfc0`

## callees

- `0x18003d78c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d7f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d7f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d7ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d7ce`

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
0x18003d78c  mov     [rsp+arg_0], rbx
0x18003d791  mov     [rsp+arg_8], rsi
0x18003d796  push    rdi
0x18003d797  sub     rsp, 20h
0x18003d79b  cmp     qword ptr [rcx+30h], 0
0x18003d7a0  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIEnrollmentInfoEnumerator@@@; const EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'}
0x18003d7a7  mov     [rcx], rax
0x18003d7aa  mov     rbx, rcx
0x18003d7ad  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIAttachEnrollEngine@@@; const EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'}
0x18003d7b4  mov     [rcx+8], rax
0x18003d7b8  jz      short loc_18003D805
0x18003d7ba  xor     edi, edi
0x18003d7bc  cmp     [rcx+28h], edi
0x18003d7bf  jbe     short loc_18003D7ED
0x18003d7c1  mov     rax, [rbx+30h]
0x18003d7c5  mov     rcx, [rax+rdi*8]; bstrString
0x18003d7c9  test    rcx, rcx
0x18003d7cc  jz      short loc_18003D7E6
0x18003d7ce  call    cs:__imp_SysFreeString
0x18003d7d5  nop     dword ptr [rax+rax+00h]
0x18003d7da  mov     rax, [rbx+30h]
0x18003d7de  mov     qword ptr [rax+rdi*8], 0
0x18003d7e6  inc     edi
0x18003d7e8  cmp     edi, [rbx+28h]
0x18003d7eb  jb      short loc_18003D7C1
0x18003d7ed  mov     rcx, [rbx+30h]; pv
0x18003d7f1  call    cs:__imp_CoTaskMemFree
0x18003d7f8  nop     dword ptr [rax+rax+00h]
0x18003d7fd  mov     qword ptr [rbx+30h], 0
0x18003d805  mov     rbx, [rsp+28h+arg_0]
0x18003d80a  mov     rsi, [rsp+28h+arg_8]
0x18003d80f  add     rsp, 20h
0x18003d813  pop     rdi
0x18003d814  retn
```
