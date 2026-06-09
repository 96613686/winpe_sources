# CComponentData::_CreateLogSet(IDataObject *,__int64,__int64)

- ea: `0x180007488`
- end: `0x1800075e9`
- name: `?_CreateLogSet@CComponentData@@AEAAJPEAUIDataObject@@_J1@Z`
- size: `353`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, struct IDataObject *, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007990`
- `0x180008890`

## callees

- `0x180002928`
- `0x18000726c`
- `0x180007488`
- `0x180015e78`
- `0x18001f57c`
- `0x180022292`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800074e9`
- `msvcrt!_wcsicmp` at `0x1800074e9`
- `msvcrt!wcscpy_s` at `0x1800075a5`
- `msvcrt!wcscpy_s` at `0x1800075a5`
- `KERNEL32!GlobalFree` at `0x1800075d3`
- `KERNEL32!GlobalFree` at `0x1800075d3`
- `USER32!RegisterClipboardFormatW` at `0x1800074b2`
- `USER32!RegisterClipboardFormatW` at `0x1800074b2`

## pseudocode

```c
int __fastcall CComponentData::_CreateLogSet(CComponentData *this, struct IDataObject *a2, __int64 a3, __int64 a4)
{
  UINT v8; // eax
  int result; // eax
  int v10; // esi
  __int64 i; // rbx
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  const wchar_t *v14; // r8
  wchar_t *String1[9]; // [rsp+20h] [rbp-48h] BYREF

  String1[0] = 0;
  v8 = RegisterClipboardFormatW(L"CCF_SZNODETYPE");
  result = ExtractFromDataObject(a2, v8, 0x50u, (void **)String1);
  v10 = result;
  if ( result >= 0 )
  {
    for ( i = *((_QWORD *)this + 10); i; i = *(_QWORD *)(i + 8) )
    {
      if ( !_wcsicmp(String1[0], (const wchar_t *)(i + 56)) && *(_QWORD *)(i + 48) == a4 )
      {
        *(_QWORD *)(i + 40) = a3;
        *(_QWORD *)(i + 48) = a4;
        if ( (*((_BYTE *)this + 56) & 0x10) != 0 )
          CLogSet::GetViewsFromDataObject((CLogSet *)i, a2);
        goto LABEL_14;
      }
    }
    v12 = (wchar_t *)operator new(0x90u);
    String1[1] = v12;
    v13 = v12;
    if ( v12 )
    {
      *((_QWORD *)v12 + 1) = 0;
      *((_QWORD *)v12 + 2) = 0;
      v12[12] = 0;
      *(_QWORD *)v12 = &CLogSet::`vftable';
      *((_QWORD *)v12 + 4) = this;
      *((_QWORD *)v12 + 5) = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 17) = 0;
      memset_0(v12 + 28, 0, 0x50u);
      v14 = String1[0];
      *((_QWORD *)v13 + 5) = a3;
      *((_QWORD *)v13 + 6) = a4;
      wcscpy_s(v13 + 28, 0x28u, v14);
      if ( (*((_BYTE *)this + 56) & 0x10) != 0 )
        CLogSet::GetViewsFromDataObject((CLogSet *)v13, a2);
      CComponentData::_AddLogSetToList(this, (struct CLogSet *)v13);
    }
    else
    {
      v10 = -2147024882;
    }
LABEL_14:
    GlobalFree(String1[0]);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180007488  push    rbx
0x18000748a  push    rsi
0x18000748b  push    rdi
0x18000748c  push    r12
0x18000748e  push    r14
0x180007490  push    r15
0x180007492  sub     rsp, 38h
0x180007496  mov     rdi, rcx
0x180007499  mov     [rsp+68h+String1], 0
0x1800074a2  lea     rcx, aCcfSznodetype; "CCF_SZNODETYPE"
0x1800074a9  mov     r14, r9
0x1800074ac  mov     r12, r8
0x1800074af  mov     r15, rdx
0x1800074b2  call    cs:__imp_RegisterClipboardFormatW
0x1800074b8  lea     r9, [rsp+68h+String1]; void **
0x1800074bd  mov     r8d, 50h ; 'P'; unsigned int
0x1800074c3  mov     edx, eax; unsigned int
0x1800074c5  mov     rcx, r15; struct IDataObject *
0x1800074c8  call    ?ExtractFromDataObject@@YAJPEAUIDataObject@@IKPEAPEAX@Z; ExtractFromDataObject(IDataObject *,uint,ulong,void * *)
0x1800074cd  mov     esi, eax
0x1800074cf  test    eax, eax
0x1800074d1  js      loc_1800075DB
0x1800074d7  mov     rbx, [rdi+50h]
0x1800074db  test    rbx, rbx
0x1800074de  jz      short loc_180007521
0x1800074e0  mov     rcx, [rsp+68h+String1]; String1
0x1800074e5  lea     rdx, [rbx+38h]; String2
0x1800074e9  call    cs:__imp__wcsicmp
0x1800074ef  test    eax, eax
0x1800074f1  jnz     short loc_1800074F9
0x1800074f3  cmp     [rbx+30h], r14
0x1800074f7  jz      short loc_1800074FF
0x1800074f9  mov     rbx, [rbx+8]
0x1800074fd  jmp     short loc_1800074DB
0x1800074ff  mov     [rbx+28h], r12
0x180007503  mov     [rbx+30h], r14
0x180007507  test    byte ptr [rdi+38h], 10h
0x18000750b  jz      loc_1800075CE
0x180007511  mov     rdx, r15; struct IDataObject *
0x180007514  mov     rcx, rbx; this
0x180007517  call    ?GetViewsFromDataObject@CLogSet@@QEAAXPEAUIDataObject@@@Z; CLogSet::GetViewsFromDataObject(IDataObject *)
0x18000751c  jmp     loc_1800075CE
0x180007521  mov     ecx, 90h; Size
0x180007526  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000752b  mov     [rsp+68h+var_40], rax
0x180007530  mov     rbx, rax
0x180007533  test    rax, rax
0x180007536  jz      loc_1800075C9
0x18000753c  mov     qword ptr [rax+8], 0
0x180007544  lea     rcx, [rbx+38h]; void *
0x180007548  mov     qword ptr [rax+10h], 0
0x180007550  xor     edx, edx; Val
0x180007552  xor     eax, eax
0x180007554  mov     [rbx+18h], ax
0x180007558  lea     rax, ??_7CLogSet@@6B@; const CLogSet::`vftable'
0x18000755f  mov     [rbx], rax
0x180007562  lea     r8d, [rdx+50h]; Size
0x180007566  mov     [rbx+20h], rdi
0x18000756a  mov     qword ptr [rbx+28h], 0
0x180007572  mov     qword ptr [rbx+30h], 0
0x18000757a  mov     qword ptr [rbx+88h], 0
0x180007585  call    memset_0
0x18000758a  test    rbx, rbx
0x18000758d  jz      short loc_1800075C9
0x18000758f  mov     r8, [rsp+68h+String1]; Source
0x180007594  lea     rcx, [rbx+38h]; Destination
0x180007598  mov     edx, 28h ; '('; SizeInWords
0x18000759d  mov     [rbx+28h], r12
0x1800075a1  mov     [rbx+30h], r14
0x1800075a5  call    cs:__imp_wcscpy_s
0x1800075ab  test    byte ptr [rdi+38h], 10h
0x1800075af  jz      short loc_1800075BC
0x1800075b1  mov     rdx, r15; struct IDataObject *
0x1800075b4  mov     rcx, rbx; this
0x1800075b7  call    ?GetViewsFromDataObject@CLogSet@@QEAAXPEAUIDataObject@@@Z; CLogSet::GetViewsFromDataObject(IDataObject *)
0x1800075bc  mov     rdx, rbx; struct CLogSet *
0x1800075bf  mov     rcx, rdi; this
0x1800075c2  call    ?_AddLogSetToList@CComponentData@@AEAAXPEAVCLogSet@@@Z; CComponentData::_AddLogSetToList(CLogSet *)
0x1800075c7  jmp     short loc_1800075CE
0x1800075c9  mov     esi, 8007000Eh
0x1800075ce  mov     rcx, [rsp+68h+String1]; hMem
0x1800075d3  call    cs:__imp_GlobalFree
0x1800075d9  mov     eax, esi
0x1800075db  add     rsp, 38h
0x1800075df  pop     r15
0x1800075e1  pop     r14
0x1800075e3  pop     r12
0x1800075e5  pop     rdi
0x1800075e6  pop     rsi
0x1800075e7  pop     rbx
0x1800075e8  retn
```
