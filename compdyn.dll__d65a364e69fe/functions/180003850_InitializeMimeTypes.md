# InitializeMimeTypes

- ea: `0x180003850`
- end: `0x180003a7a`
- name: `InitializeMimeTypes`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003620`

## callees

- `0x180001960`
- `0x180003850`
- `0x180003a80`
- `0x180004210`
- `0x180004bde`
- `0x180008010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@XZ` at `0x1800039ac`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800039b6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800039ac`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800039b6`

## pseudocode

```c
__int64 __fastcall InitializeMimeTypes(__int64 a1, __int64 a2, struct _LIST_ENTRY *a3, int *a4)
{
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rax
  int v7; // edi
  unsigned int v8; // esi
  char *v9; // rax
  char *v10; // rbx
  unsigned int v11; // edx
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-28h] BYREF
  int v18; // [rsp+90h] [rbp+18h] BYREF

  v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a1 + 32LL);
  v15 = 0;
  v16 = 0;
  v14 = 0;
  v13 = 0;
  String1 = 0;
  v18 = 0;
  v7 = v5(a1, a2, &v16);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 40LL))(v16, &v15);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 24LL))(v15, &v13);
      if ( v7 >= 0 )
      {
        v8 = 0;
        if ( v13 )
        {
          while ( 1 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 32LL))(v15, v8, &v14);
            if ( v7 < 0 )
              break;
            v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                   v14,
                   L"mimeType",
                   &String1,
                   0,
                   0);
            if ( v7 < 0 )
              break;
            v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                   v14,
                   L"enabled",
                   &v18,
                   0,
                   0);
            if ( v7 < 0 )
              break;
            if ( !wcscmp_0(String1, L"*/*") )
            {
              *a4 = v18;
            }
            else
            {
              v9 = (char *)operator new(0x90u);
              v10 = v9;
              if ( !v9 )
              {
                v7 = -2147024888;
                break;
              }
              STRA::STRA((STRA *)(v9 + 16));
              STRA::STRA((STRA *)(v10 + 72));
              v7 = CONTENT_TYPE_ALLOWED_ENTRY::Initialize((CONTENT_TYPE_ALLOWED_ENTRY *)v10, String1, v18, a3);
              if ( v7 < 0 )
              {
                CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'((CONTENT_TYPE_ALLOWED_ENTRY *)v10, v11);
                break;
              }
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            ++v8;
            v14 = 0;
            if ( v8 >= v13 )
              goto LABEL_12;
          }
        }
        else
        {
LABEL_12:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v15 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v16 = 0;
        }
      }
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003850  push    rbp
0x180003852  push    rdi
0x180003853  mov     rbp, rsp
0x180003856  sub     rsp, 78h
0x18000385a  mov     rax, [rcx]
0x18000385d  mov     [rsp+78h+var_8], r12
0x180003862  xor     r12d, r12d
0x180003865  mov     [rsp+78h+var_10], r14
0x18000386a  mov     r14, r8
0x18000386d  mov     [rsp+78h+var_18], r15
0x180003872  lea     r8, [rbp+var_30]
0x180003876  mov     rax, [rax+20h]
0x18000387a  mov     r15, r9
0x18000387d  mov     [rbp+var_38], r12
0x180003881  mov     [rbp+var_30], r12
0x180003885  mov     [rbp+var_40], r12
0x180003889  mov     [rbp+var_48], r12d
0x18000388d  mov     [rbp+String1], r12
0x180003891  mov     [rbp+arg_0], r12d
0x180003895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389a  mov     edi, eax
0x18000389c  test    eax, eax
0x18000389e  js      loc_180003A30
0x1800038a4  mov     rcx, [rbp+var_30]
0x1800038a8  lea     rdx, [rbp+var_38]
0x1800038ac  mov     rax, [rcx]
0x1800038af  mov     rax, [rax+28h]
0x1800038b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b8  mov     edi, eax
0x1800038ba  test    eax, eax
0x1800038bc  js      loc_180003A30
0x1800038c2  mov     rcx, [rbp+var_38]
0x1800038c6  lea     rdx, [rbp+var_48]
0x1800038ca  mov     rax, [rcx]
0x1800038cd  mov     rax, [rax+18h]
0x1800038d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d6  mov     edi, eax
0x1800038d8  test    eax, eax
0x1800038da  js      loc_180003A30
0x1800038e0  mov     [rsp+78h+arg_10], rsi
0x1800038e8  mov     esi, r12d
0x1800038eb  mov     [rsp+78h+arg_8], rbx
0x1800038f3  cmp     [rbp+var_48], r12d
0x1800038f7  jbe     loc_1800039F8
0x1800038fd  nop     dword ptr [rax]
0x180003900  mov     rcx, [rbp+var_38]
0x180003904  lea     r8, [rbp+var_40]
0x180003908  mov     edx, esi
0x18000390a  mov     rax, [rcx]
0x18000390d  mov     rax, [rax+20h]
0x180003911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003916  mov     edi, eax
0x180003918  test    eax, eax
0x18000391a  js      loc_180003A20
0x180003920  mov     rcx, [rbp+var_40]
0x180003924  lea     r8, [rbp+String1]
0x180003928  xor     r9d, r9d
0x18000392b  mov     [rsp+78h+var_58], r12
0x180003930  lea     rdx, aMimetype; "mimeType"
0x180003937  mov     rax, [rcx]
0x18000393a  mov     rax, [rax+40h]
0x18000393e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003943  mov     edi, eax
0x180003945  test    eax, eax
0x180003947  js      loc_180003A20
0x18000394d  mov     rcx, [rbp+var_40]
0x180003951  lea     r8, [rbp+arg_0]
0x180003955  xor     r9d, r9d
0x180003958  mov     [rsp+78h+var_58], r12
0x18000395d  lea     rdx, aEnabled; "enabled"
0x180003964  mov     rax, [rcx]
0x180003967  mov     rax, [rax+48h]
0x18000396b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003970  mov     edi, eax
0x180003972  test    eax, eax
0x180003974  js      loc_180003A20
0x18000397a  mov     rcx, [rbp+String1]; String1
0x18000397e  lea     rdx, String2; "*/*"
0x180003985  call    wcscmp_0
0x18000398a  test    eax, eax
0x18000398c  jz      loc_180003A6F
0x180003992  mov     ecx, 90h; Size
0x180003997  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000399c  mov     rbx, rax
0x18000399f  test    rax, rax
0x1800039a2  jz      loc_1800058FC
0x1800039a8  lea     rcx, [rax+10h]
0x1800039ac  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800039b2  lea     rcx, [rbx+48h]
0x1800039b6  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800039bc  mov     r8d, [rbp+arg_0]; int
0x1800039c0  mov     r9, r14; struct _LIST_ENTRY *
0x1800039c3  mov     rdx, [rbp+String1]; unsigned __int16 *
0x1800039c7  mov     rcx, rbx; this
0x1800039ca  call    ?Initialize@CONTENT_TYPE_ALLOWED_ENTRY@@QEAAJPEBGHPEAU_LIST_ENTRY@@@Z; CONTENT_TYPE_ALLOWED_ENTRY::Initialize(ushort const *,int,_LIST_ENTRY *)
0x1800039cf  mov     edi, eax
0x1800039d1  test    eax, eax
0x1800039d3  js      loc_1800058EE
0x1800039d9  mov     rcx, [rbp+var_40]
0x1800039dd  mov     rax, [rcx]
0x1800039e0  mov     rax, [rax+10h]
0x1800039e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e9  inc     esi
0x1800039eb  mov     [rbp+var_40], r12
0x1800039ef  cmp     esi, [rbp+var_48]
0x1800039f2  jb      loc_180003900
0x1800039f8  mov     rcx, [rbp+var_38]
0x1800039fc  mov     rax, [rcx]
0x1800039ff  mov     rax, [rax+10h]
0x180003a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a08  mov     rcx, [rbp+var_30]
0x180003a0c  mov     [rbp+var_38], r12
0x180003a10  mov     rax, [rcx]
0x180003a13  mov     rax, [rax+10h]
0x180003a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1c  mov     [rbp+var_30], r12
0x180003a20  mov     rbx, [rsp+78h+arg_8]
0x180003a28  mov     rsi, [rsp+78h+arg_10]
0x180003a30  mov     rcx, [rbp+var_40]
0x180003a34  mov     r15, [rsp+78h+var_18]
0x180003a39  mov     r14, [rsp+78h+var_10]
0x180003a3e  test    rcx, rcx
0x180003a41  jnz     loc_180005906
0x180003a47  mov     rcx, [rbp+var_38]
0x180003a4b  test    rcx, rcx
0x180003a4e  jnz     loc_18000591B
0x180003a54  mov     rcx, [rbp+var_30]
0x180003a58  mov     r12, [rsp+78h+var_8]
0x180003a5d  test    rcx, rcx
0x180003a60  jnz     loc_180005930
0x180003a66  mov     eax, edi
0x180003a68  add     rsp, 78h
0x180003a6c  pop     rdi
0x180003a6d  pop     rbp
0x180003a6e  retn
0x180003a6f  mov     eax, [rbp+arg_0]
0x180003a72  mov     [r15], eax
0x180003a75  jmp     loc_1800039D9
0x1800058ee  mov     rcx, rbx; this
0x1800058f1  call    ??_GCONTENT_TYPE_ALLOWED_ENTRY@@QEAAPEAXI@Z; CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'(uint)
0x1800058f6  nop
0x1800058f7  jmp     loc_180003A20
0x1800058fc  mov     edi, 80070008h
0x180005901  jmp     loc_180003A20
0x180005906  mov     rax, [rcx]
0x180005909  mov     rax, [rax+10h]
0x18000590d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005912  mov     [rbp+var_40], r12
0x180005916  jmp     loc_180003A47
0x18000591b  mov     rax, [rcx]
0x18000591e  mov     rax, [rax+10h]
0x180005922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005927  mov     [rbp+var_38], r12
0x18000592b  jmp     loc_180003A54
0x180005930  mov     rax, [rcx]
0x180005933  mov     rax, [rax+10h]
0x180005937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593c  nop
0x18000593d  jmp     loc_180003A66
```
