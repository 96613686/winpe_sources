# CWMWriterProperties::GetVideoInputNumber(ulong *)

- ea: `0x1800126e0`
- end: `0x180012838`
- name: `?GetVideoInputNumber@CWMWriterProperties@@AEAAJPEAK@Z`
- size: `344`
- prototype: `__int64 __fastcall(CWMWriterProperties *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012c00`

## callees

- `0x180001460`
- `0x1800071e8`
- `0x1800126e0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterProperties::GetVideoInputNumber(CWMWriterProperties *this, unsigned int *a2)
{
  __int64 v2; // rcx
  unsigned int v4; // edi
  int v5; // ebx
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v9; // [rsp+30h] [rbp-30h] BYREF
  __int64 v10; // [rsp+38h] [rbp-28h] BYREF
  __int64 v11; // [rsp+40h] [rbp-20h] BYREF
  struct _AMMediaType *pv; // [rsp+48h] [rbp-18h] BYREF
  int v13; // [rsp+50h] [rbp-10h] BYREF

  v2 = *((_QWORD *)this + 13);
  v11 = 0;
  v9 = 0;
  v4 = -1;
  v13 = 0;
  v5 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 80LL))(v2, &v11) >= 0 )
  {
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v11 + 24LL))(
               v11,
               1,
               &v9,
               &v13) )
    {
      pv = 0;
      ++v4;
      v10 = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 96LL))(v9, &v10);
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct _AMMediaType **, int *))(*(_QWORD *)v10 + 24LL))(
              v10,
              1,
              &pv,
              &v13) )
      {
        v6 = *(_QWORD *)&pv->majortype.Data1 - *(_QWORD *)&MEDIATYPE_Video.Data1;
        if ( *(_QWORD *)&pv->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Video.Data1 )
          v6 = *(_QWORD *)pv->majortype.Data4 - *(_QWORD *)MEDIATYPE_Video.Data4;
        if ( !v6 )
          v5 = 1;
        DeleteMediaType(pv);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v5 )
      {
        *a2 = v4;
        v7 = 0;
        goto LABEL_12;
      }
    }
  }
  v7 = -2147467259;
LABEL_12:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return v7;
}

```

## disassembly

```asm
0x1800126e0  mov     [rsp-18h+arg_10], rbx
0x1800126e5  mov     [rsp-18h+arg_18], rsi
0x1800126ea  push    rbp
0x1800126eb  push    rdi
0x1800126ec  push    r15
0x1800126ee  mov     rbp, rsp
0x1800126f1  sub     rsp, 60h
0x1800126f5  mov     rax, cs:__security_cookie
0x1800126fc  xor     rax, rsp
0x1800126ff  mov     [rbp+var_8], rax
0x180012703  mov     rcx, [rcx+68h]
0x180012707  mov     rsi, rdx
0x18001270a  mov     [rbp+var_20], 0
0x180012712  lea     rdx, [rbp+var_20]
0x180012716  mov     [rbp+var_30], 0
0x18001271e  or      edi, 0FFFFFFFFh
0x180012721  mov     [rbp+var_10], 0
0x180012728  xor     ebx, ebx
0x18001272a  mov     rax, [rcx]
0x18001272d  mov     rax, [rax+50h]
0x180012731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012736  test    eax, eax
0x180012738  js      loc_180012800
0x18001273e  lea     r15d, [rbx+1]
0x180012742  mov     rcx, [rbp+var_20]
0x180012746  lea     r9, [rbp+var_10]
0x18001274a  lea     r8, [rbp+var_30]
0x18001274e  mov     edx, r15d
0x180012751  mov     rax, [rcx]
0x180012754  mov     rax, [rax+18h]
0x180012758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001275d  test    eax, eax
0x18001275f  jnz     loc_180012800
0x180012765  mov     rcx, [rbp+var_30]
0x180012769  lea     rdx, [rbp+var_28]
0x18001276d  mov     [rbp+pv], 0
0x180012775  add     edi, r15d
0x180012778  mov     [rbp+var_28], 0
0x180012780  mov     rax, [rcx]
0x180012783  mov     rax, [rax+60h]
0x180012787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001278c  mov     rcx, [rbp+var_28]
0x180012790  lea     r9, [rbp+var_10]
0x180012794  lea     r8, [rbp+pv]
0x180012798  mov     edx, r15d
0x18001279b  mov     rax, [rcx]
0x18001279e  mov     rax, [rax+18h]
0x1800127a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a7  test    eax, eax
0x1800127a9  jnz     short loc_1800127D2
0x1800127ab  mov     rcx, [rbp+pv]; pv
0x1800127af  mov     rax, [rcx]
0x1800127b2  sub     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x1800127b9  jnz     short loc_1800127C6
0x1800127bb  mov     rax, [rcx+8]
0x1800127bf  sub     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x1800127c6  test    rax, rax
0x1800127c9  cmovz   ebx, r15d
0x1800127cd  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800127d2  mov     rcx, [rbp+var_30]
0x1800127d6  mov     rax, [rcx]
0x1800127d9  mov     rax, [rax+10h]
0x1800127dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127e2  mov     rcx, [rbp+var_28]
0x1800127e6  mov     rax, [rcx]
0x1800127e9  mov     rax, [rax+10h]
0x1800127ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127f2  test    ebx, ebx
0x1800127f4  jz      loc_180012742
0x1800127fa  mov     [rsi], edi
0x1800127fc  xor     ebx, ebx
0x1800127fe  jmp     short loc_180012805
0x180012800  mov     ebx, 80004005h
0x180012805  mov     rcx, [rbp+var_20]
0x180012809  mov     rdx, [rcx]
0x18001280c  mov     rax, [rdx+10h]
0x180012810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012815  mov     eax, ebx
0x180012817  mov     rcx, [rbp+var_8]
0x18001281b  xor     rcx, rsp; StackCookie
0x18001281e  call    __security_check_cookie
0x180012823  lea     r11, [rsp+60h+var_s0]
0x180012828  mov     rbx, [r11+30h]
0x18001282c  mov     rsi, [r11+38h]
0x180012830  mov     rsp, r11
0x180012833  pop     r15
0x180012835  pop     rdi
0x180012836  pop     rbp
0x180012837  retn
```
