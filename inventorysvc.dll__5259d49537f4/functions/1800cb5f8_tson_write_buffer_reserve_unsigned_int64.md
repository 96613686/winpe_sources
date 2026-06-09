# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800cb5f8`
- end: `0x1800cb6f1`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c712c`
- `0x1800c769c`
- `0x1800c7734`
- `0x1800c77c8`
- `0x1800c7948`
- `0x1800c7e54`
- `0x1800caa1c`
- `0x1800cb548`
- `0x1800cb6f8`
- `0x1800cbd94`
- `0x1800cc2e0`
- `0x1800cc81c`
- `0x1800cca30`

## callees

- `0x1800037d2`
- `0x1800038b8`
- `0x180005477`
- `0x1800cb5f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800cb675`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800cb688`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800cb675`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800cb688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb6b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb6ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb6ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cb624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cb624`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // r14
  char *v4; // rax
  char *v5; // rbp
  __int64 v6; // rbx
  size_t v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  void *v11; // r15
  DWORD LastError; // ebx
  bool result; // al

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( !v4 )
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  v6 = *((_QWORD *)this + 258);
  v7 = *((_QWORD *)this + 259) - v6;
  if ( v7 )
  {
    if ( !v6 || v3 < v7 )
    {
      memset_0(v4, 0, v3);
      if ( v6 )
      {
        if ( v3 >= v7 )
          goto LABEL_13;
        *(_DWORD *)_o__errno(v9, v8, v10) = 34;
      }
      else
      {
        *(_DWORD *)_o__errno(v9, v8, v10) = 22;
      }
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    memcpy_0(v4, *((const void **)this + 258), v7);
  }
LABEL_13:
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v5;
  *((_QWORD *)this + 259) = &v5[v7];
  *((_QWORD *)this + 260) = &v5[v3];
  result = 1;
  *((_QWORD *)this + 258) = v5;
  return result;
}

```

## disassembly

```asm
0x1800cb5f8  push    rbx
0x1800cb5fa  push    rbp
0x1800cb5fb  push    rsi
0x1800cb5fc  push    rdi
0x1800cb5fd  push    r14
0x1800cb5ff  push    r15
0x1800cb601  sub     rsp, 28h
0x1800cb605  mov     rax, [rcx+820h]
0x1800cb60c  mov     rdi, rcx
0x1800cb60f  sub     rax, [rcx+810h]
0x1800cb616  cmp     rax, rdx
0x1800cb619  cmova   rdx, rax
0x1800cb61d  lea     r14, [rdx+rdx]
0x1800cb621  mov     rcx, r14; cb
0x1800cb624  call    cs:__imp_CoTaskMemAlloc
0x1800cb62a  mov     rbp, rax
0x1800cb62d  test    rax, rax
0x1800cb630  jz      loc_1800CB6DE
0x1800cb636  mov     rbx, [rdi+810h]
0x1800cb63d  mov     rsi, [rdi+818h]
0x1800cb644  sub     rsi, rbx
0x1800cb647  jz      short loc_1800CB699
0x1800cb649  test    rbx, rbx
0x1800cb64c  jz      short loc_1800CB663
0x1800cb64e  cmp     r14, rsi
0x1800cb651  jb      short loc_1800CB663
0x1800cb653  mov     r8, rsi; Size
0x1800cb656  mov     rdx, rbx; Src
0x1800cb659  mov     rcx, rax; void *
0x1800cb65c  call    memcpy_0
0x1800cb661  jmp     short loc_1800CB699
0x1800cb663  mov     r8, r14; Size
0x1800cb666  xor     edx, edx; Val
0x1800cb668  mov     rcx, rbp; void *
0x1800cb66b  call    memset_0
0x1800cb670  test    rbx, rbx
0x1800cb673  jnz     short loc_1800CB683
0x1800cb675  call    cs:__imp__o__errno
0x1800cb67b  mov     dword ptr [rax], 16h
0x1800cb681  jmp     short loc_1800CB694
0x1800cb683  cmp     r14, rsi
0x1800cb686  jnb     short loc_1800CB699
0x1800cb688  call    cs:__imp__o__errno
0x1800cb68e  mov     dword ptr [rax], 22h ; '"'
0x1800cb694  call    _invalid_parameter_noinfo
0x1800cb699  mov     r15, [rdi]
0x1800cb69c  test    r15, r15
0x1800cb69f  jz      short loc_1800CB6BA
0x1800cb6a1  call    cs:__imp_GetLastError
0x1800cb6a7  mov     rcx, r15; pv
0x1800cb6aa  mov     ebx, eax
0x1800cb6ac  call    cs:__imp_CoTaskMemFree
0x1800cb6b2  mov     ecx, ebx; dwErrCode
0x1800cb6b4  call    cs:__imp_SetLastError
0x1800cb6ba  mov     [rdi], rbp
0x1800cb6bd  lea     rax, [rsi+rbp]
0x1800cb6c1  mov     [rdi+818h], rax
0x1800cb6c8  lea     rax, [r14+rbp]
0x1800cb6cc  mov     [rdi+820h], rax
0x1800cb6d3  mov     al, 1
0x1800cb6d5  mov     [rdi+810h], rbp
0x1800cb6dc  jmp     short loc_1800CB6E4
0x1800cb6de  mov     byte ptr [rdi+8], 1
0x1800cb6e2  xor     al, al
0x1800cb6e4  add     rsp, 28h
0x1800cb6e8  pop     r15
0x1800cb6ea  pop     r14
0x1800cb6ec  pop     rdi
0x1800cb6ed  pop     rsi
0x1800cb6ee  pop     rbp
0x1800cb6ef  pop     rbx
0x1800cb6f0  retn
```
