# RenameNfsClientGroup(ushort const *,ushort const *,CNfsTaskContext *)

- ea: `0x180027190`
- end: `0x180027299`
- name: `?RenameNfsClientGroup@@YAKPEBG0PEAVCNfsTaskContext@@@Z`
- size: `265`
- prototype: `unsigned int __fastcall(wchar_t *String1, const unsigned __int16 *, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180015c0c`

## callees

- `0x180006a54`
- `0x1800219fc`
- `0x180026970`
- `0x180026ac4`
- `0x180027190`
- `0x1800272a0`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800271f1`
- `msvcrt!_wcsicmp` at `0x180027209`
- `msvcrt!_wcsicmp` at `0x1800271f1`
- `msvcrt!_wcsicmp` at `0x180027209`

## pseudocode

```c
__int64 __fastcall RenameNfsClientGroup(wchar_t *String1, wchar_t *a2, struct CNfsTaskContext *a3)
{
  unsigned int ErrorFromHr; // ebx
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v8; // rsi
  struct _LIST_ENTRY *v9; // r12
  wchar_t *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  struct _LIST_ENTRY v15; // [rsp+30h] [rbp-58h] BYREF

  v15.Blink = &v15;
  v15.Flink = &v15;
  ErrorFromHr = LoadCliGrpData(&v15, 0);
  if ( !ErrorFromHr )
  {
    Flink = v15.Flink;
    v8 = 0;
    ErrorFromHr = 1168;
    while ( Flink != &v15 )
    {
      v9 = Flink->Flink;
      if ( _wcsicmp(String1, (const wchar_t *)&Flink[2].Flink + 2) )
      {
        if ( !_wcsicmp(a2, (const wchar_t *)&Flink[2].Flink + 2) )
        {
          ErrorFromHr = 183;
          v10 = a2;
          v11 = 183;
          v12 = 3221229607LL;
LABEL_13:
          (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, wchar_t *))(*(_QWORD *)a3 + 40LL))(
            a3,
            v11,
            v12,
            v10);
          goto LABEL_14;
        }
      }
      else
      {
        v8 = Flink;
        ErrorFromHr = 0;
      }
      Flink = v9;
    }
    if ( ErrorFromHr )
    {
      v10 = String1;
      v11 = 1168;
      v12 = 3221229608LL;
      goto LABEL_13;
    }
    v13 = StringCchCopyW((unsigned __int16 *)&v8[2].Flink + 2, 0x400u, a2);
    ErrorFromHr = NfsGetErrorFromHr(v13);
    if ( !ErrorFromHr )
      ErrorFromHr = SaveSettings(&v15);
  }
LABEL_14:
  FreeGroupList(&v15);
  return ErrorFromHr;
}

```

## disassembly

```asm
0x180027190  mov     r11, rsp
0x180027193  push    rbx
0x180027194  push    rbp
0x180027195  push    rsi
0x180027196  push    rdi
0x180027197  push    r12
0x180027199  push    r13
0x18002719b  push    r14
0x18002719d  push    r15
0x18002719f  sub     rsp, 48h
0x1800271a3  lea     rax, [r11-58h]
0x1800271a7  mov     rbp, rdx
0x1800271aa  mov     [r11-50h], rax
0x1800271ae  mov     r13, rcx
0x1800271b1  lea     rax, [r11-58h]
0x1800271b5  xor     edx, edx; unsigned int *
0x1800271b7  lea     rcx, [r11-58h]; struct _LIST_ENTRY *
0x1800271bb  mov     [r11-58h], rax
0x1800271bf  mov     r14, r8
0x1800271c2  call    ?LoadCliGrpData@@YAKPEAU_LIST_ENTRY@@PEAK@Z; LoadCliGrpData(_LIST_ENTRY *,ulong *)
0x1800271c7  mov     ebx, eax
0x1800271c9  test    eax, eax
0x1800271cb  jnz     loc_18002727C
0x1800271d1  mov     rdi, [rsp+88h+var_58.Flink]
0x1800271d6  xor     esi, esi
0x1800271d8  mov     ebx, 490h
0x1800271dd  lea     rax, [rsp+88h+var_58]
0x1800271e2  cmp     rdi, rax
0x1800271e5  jz      short loc_18002722A
0x1800271e7  mov     r12, [rdi]
0x1800271ea  lea     rdx, [rdi+24h]; String2
0x1800271ee  mov     rcx, r13; String1
0x1800271f1  call    cs:__imp__wcsicmp
0x1800271f7  test    eax, eax
0x1800271f9  jnz     short loc_180027202
0x1800271fb  mov     rsi, rdi
0x1800271fe  xor     ebx, ebx
0x180027200  jmp     short loc_180027213
0x180027202  lea     rdx, [rdi+24h]; String2
0x180027206  mov     rcx, rbp; String1
0x180027209  call    cs:__imp__wcsicmp
0x18002720f  test    eax, eax
0x180027211  jz      short loc_180027218
0x180027213  mov     rdi, r12
0x180027216  jmp     short loc_1800271DD
0x180027218  mov     ebx, 0B7h
0x18002721d  mov     r9, rbp
0x180027220  mov     edx, ebx
0x180027222  mov     r8d, 0C0001027h
0x180027228  jmp     short loc_18002726D
0x18002722a  test    ebx, ebx
0x18002722c  jnz     short loc_18002725A
0x18002722e  lea     rcx, [rsi+24h]; unsigned __int16 *
0x180027232  mov     r8, rbp; unsigned __int16 *
0x180027235  mov     edx, 400h; unsigned __int64
0x18002723a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002723f  mov     ecx, eax; int
0x180027241  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x180027246  mov     ebx, eax
0x180027248  test    eax, eax
0x18002724a  jnz     short loc_18002727C
0x18002724c  lea     rcx, [rsp+88h+var_58]; struct _LIST_ENTRY *
0x180027251  call    ?SaveSettings@@YAKPEAU_LIST_ENTRY@@@Z; SaveSettings(_LIST_ENTRY *)
0x180027256  mov     ebx, eax
0x180027258  jmp     short loc_18002727C
0x18002725a  cmp     ebx, 490h
0x180027260  jnz     short loc_18002727C
0x180027262  mov     r9, r13
0x180027265  mov     edx, ebx
0x180027267  mov     r8d, 0C0001028h
0x18002726d  mov     rax, [r14]
0x180027270  mov     rcx, r14
0x180027273  mov     rax, [rax+28h]
0x180027277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002727c  lea     rcx, [rsp+88h+var_58]; struct _LIST_ENTRY *
0x180027281  call    ?FreeGroupList@@YAXPEAU_LIST_ENTRY@@@Z; FreeGroupList(_LIST_ENTRY *)
0x180027286  mov     eax, ebx
0x180027288  add     rsp, 48h
0x18002728c  pop     r15
0x18002728e  pop     r14
0x180027290  pop     r13
0x180027292  pop     r12
0x180027294  pop     rdi
0x180027295  pop     rsi
0x180027296  pop     rbp
0x180027297  pop     rbx
0x180027298  retn
```
