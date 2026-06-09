# InitializeMimeTypes

- ea: `0x1800036d0`
- end: `0x1800038fa`
- name: `InitializeMimeTypes`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800033c0`

## callees

- `0x1800036d0`
- `0x180003ba0`
- `0x180005460`
- `0x180005f5e`
- `0x180008088`
- `0x180009010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@XZ` at `0x18000382c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003836`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000382c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003836`

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
0x1800036d0  push    rbp
0x1800036d2  push    rdi
0x1800036d3  mov     rbp, rsp
0x1800036d6  sub     rsp, 78h
0x1800036da  mov     rax, [rcx]
0x1800036dd  mov     [rsp+78h+var_8], r12
0x1800036e2  xor     r12d, r12d
0x1800036e5  mov     [rsp+78h+var_10], r14
0x1800036ea  mov     r14, r8
0x1800036ed  mov     [rsp+78h+var_18], r15
0x1800036f2  lea     r8, [rbp+var_30]
0x1800036f6  mov     rax, [rax+20h]
0x1800036fa  mov     r15, r9
0x1800036fd  mov     [rbp+var_38], r12
0x180003701  mov     [rbp+var_30], r12
0x180003705  mov     [rbp+var_40], r12
0x180003709  mov     [rbp+var_48], r12d
0x18000370d  mov     [rbp+String1], r12
0x180003711  mov     [rbp+arg_0], r12d
0x180003715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000371a  mov     edi, eax
0x18000371c  test    eax, eax
0x18000371e  js      loc_1800038B0
0x180003724  mov     rcx, [rbp+var_30]
0x180003728  lea     rdx, [rbp+var_38]
0x18000372c  mov     rax, [rcx]
0x18000372f  mov     rax, [rax+28h]
0x180003733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003738  mov     edi, eax
0x18000373a  test    eax, eax
0x18000373c  js      loc_1800038B0
0x180003742  mov     rcx, [rbp+var_38]
0x180003746  lea     rdx, [rbp+var_48]
0x18000374a  mov     rax, [rcx]
0x18000374d  mov     rax, [rax+18h]
0x180003751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003756  mov     edi, eax
0x180003758  test    eax, eax
0x18000375a  js      loc_1800038B0
0x180003760  mov     [rsp+78h+arg_10], rsi
0x180003768  mov     esi, r12d
0x18000376b  mov     [rsp+78h+arg_8], rbx
0x180003773  cmp     [rbp+var_48], r12d
0x180003777  jbe     loc_180003878
0x18000377d  nop     dword ptr [rax]
0x180003780  mov     rcx, [rbp+var_38]
0x180003784  lea     r8, [rbp+var_40]
0x180003788  mov     edx, esi
0x18000378a  mov     rax, [rcx]
0x18000378d  mov     rax, [rax+20h]
0x180003791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003796  mov     edi, eax
0x180003798  test    eax, eax
0x18000379a  js      loc_1800038A0
0x1800037a0  mov     rcx, [rbp+var_40]
0x1800037a4  lea     r8, [rbp+String1]
0x1800037a8  xor     r9d, r9d
0x1800037ab  mov     [rsp+78h+var_58], r12
0x1800037b0  lea     rdx, aMimetype; "mimeType"
0x1800037b7  mov     rax, [rcx]
0x1800037ba  mov     rax, [rax+40h]
0x1800037be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c3  mov     edi, eax
0x1800037c5  test    eax, eax
0x1800037c7  js      loc_1800038A0
0x1800037cd  mov     rcx, [rbp+var_40]
0x1800037d1  lea     r8, [rbp+arg_0]
0x1800037d5  xor     r9d, r9d
0x1800037d8  mov     [rsp+78h+var_58], r12
0x1800037dd  lea     rdx, aEnabled; "enabled"
0x1800037e4  mov     rax, [rcx]
0x1800037e7  mov     rax, [rax+48h]
0x1800037eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f0  mov     edi, eax
0x1800037f2  test    eax, eax
0x1800037f4  js      loc_1800038A0
0x1800037fa  mov     rcx, [rbp+String1]; String1
0x1800037fe  lea     rdx, asc_18000AA80; "*/*"
0x180003805  call    wcscmp_0
0x18000380a  test    eax, eax
0x18000380c  jz      loc_1800038EF
0x180003812  mov     ecx, 90h; Size
0x180003817  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000381c  mov     rbx, rax
0x18000381f  test    rax, rax
0x180003822  jz      loc_180007196
0x180003828  lea     rcx, [rax+10h]
0x18000382c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003832  lea     rcx, [rbx+48h]
0x180003836  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000383c  mov     r8d, [rbp+arg_0]; int
0x180003840  mov     r9, r14; struct _LIST_ENTRY *
0x180003843  mov     rdx, [rbp+String1]; unsigned __int16 *
0x180003847  mov     rcx, rbx; this
0x18000384a  call    ?Initialize@CONTENT_TYPE_ALLOWED_ENTRY@@QEAAJPEBGHPEAU_LIST_ENTRY@@@Z; CONTENT_TYPE_ALLOWED_ENTRY::Initialize(ushort const *,int,_LIST_ENTRY *)
0x18000384f  mov     edi, eax
0x180003851  test    eax, eax
0x180003853  js      loc_180007188
0x180003859  mov     rcx, [rbp+var_40]
0x18000385d  mov     rax, [rcx]
0x180003860  mov     rax, [rax+10h]
0x180003864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003869  inc     esi
0x18000386b  mov     [rbp+var_40], r12
0x18000386f  cmp     esi, [rbp+var_48]
0x180003872  jb      loc_180003780
0x180003878  mov     rcx, [rbp+var_38]
0x18000387c  mov     rax, [rcx]
0x18000387f  mov     rax, [rax+10h]
0x180003883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003888  mov     rcx, [rbp+var_30]
0x18000388c  mov     [rbp+var_38], r12
0x180003890  mov     rax, [rcx]
0x180003893  mov     rax, [rax+10h]
0x180003897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389c  mov     [rbp+var_30], r12
0x1800038a0  mov     rbx, [rsp+78h+arg_8]
0x1800038a8  mov     rsi, [rsp+78h+arg_10]
0x1800038b0  mov     rcx, [rbp+var_40]
0x1800038b4  mov     r15, [rsp+78h+var_18]
0x1800038b9  mov     r14, [rsp+78h+var_10]
0x1800038be  test    rcx, rcx
0x1800038c1  jnz     loc_1800071A0
0x1800038c7  mov     rcx, [rbp+var_38]
0x1800038cb  test    rcx, rcx
0x1800038ce  jnz     loc_1800071B5
0x1800038d4  mov     rcx, [rbp+var_30]
0x1800038d8  mov     r12, [rsp+78h+var_8]
0x1800038dd  test    rcx, rcx
0x1800038e0  jnz     loc_1800071CA
0x1800038e6  mov     eax, edi
0x1800038e8  add     rsp, 78h
0x1800038ec  pop     rdi
0x1800038ed  pop     rbp
0x1800038ee  retn
0x1800038ef  mov     eax, [rbp+arg_0]
0x1800038f2  mov     [r15], eax
0x1800038f5  jmp     loc_180003859
0x180007188  mov     rcx, rbx; this
0x18000718b  call    ??_GCONTENT_TYPE_ALLOWED_ENTRY@@QEAAPEAXI@Z; CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'(uint)
0x180007190  nop
0x180007191  jmp     loc_1800038A0
0x180007196  mov     edi, 80070008h
0x18000719b  jmp     loc_1800038A0
0x1800071a0  mov     rax, [rcx]
0x1800071a3  mov     rax, [rax+10h]
0x1800071a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ac  mov     [rbp+var_40], r12
0x1800071b0  jmp     loc_1800038C7
0x1800071b5  mov     rax, [rcx]
0x1800071b8  mov     rax, [rax+10h]
0x1800071bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c1  mov     [rbp+var_38], r12
0x1800071c5  jmp     loc_1800038D4
0x1800071ca  mov     rax, [rcx]
0x1800071cd  mov     rax, [rax+10h]
0x1800071d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d6  nop
0x1800071d7  jmp     loc_1800038E6
```
