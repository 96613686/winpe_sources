# DeleteMediaTypeFile

- ea: `0x18000277c`
- end: `0x1800028a8`
- name: `DeleteMediaTypeFile`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180001ee0`

## callees

- `0x180001014`
- `0x180001460`
- `0x1800020b0`
- `0x1800021ec`
- `0x180002450`
- `0x18000277c`
- `0x18001f010`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x1800027c3`
- `ADVAPI32!RegDeleteKeyW` at `0x180002872`
- `ADVAPI32!RegDeleteKeyW` at `0x1800027c3`
- `ADVAPI32!RegDeleteKeyW` at `0x180002872`

## pseudocode

```c
LSTATUS __fastcall DeleteMediaTypeFile(const struct _GUID *a1, const struct _GUID *a2, __int64 a3, unsigned int a4)
{
  LSTATUS result; // eax
  const struct _GUID *v5; // rcx
  unsigned int v6; // r9d
  bool v7; // cc
  HKEY v8; // rdx
  void **v9; // rdx
  void *v10; // rax
  int v11; // eax
  int v12; // ebx
  int v13; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+28h] [rbp-D8h]
  int v15[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[11]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+9Ch] [rbp-64h]
  WCHAR SubKey[200]; // [rsp+B0h] [rbp-50h] BYREF

  result = GetMediaTypePath(a1, a2, SubKey, a4);
  if ( result >= 0 )
  {
    result = RegDeleteKeyW(HKEY_CLASSES_ROOT, SubKey);
    v7 = result <= 0;
    if ( !result )
    {
      result = GetMediaTypePath(v5, 0, SubKey, v6);
      v15[0] = result;
      if ( result < 0 )
        return result;
      CKey::CKey((CKey *)v16, v8, SubKey, v15, v13, v14);
      v9 = &CEnumKey::`vftable';
      v16[0] = &CEnumKey::`vftable';
      if ( v15[0] >= 0 && (unsigned int)(v17 + 1) > 0x1E )
      {
        v10 = operator new[](saturated_mul((unsigned int)(v17 + 1), 2u));
        v9 = (void **)v16[0];
        v16[10] = v10;
      }
      v11 = ((__int64 (__fastcall *)(_QWORD *))*v9)(v16);
      v16[0] = &CEnumKey::`vftable';
      v12 = v11;
      CKey::~CKey((CKey *)v16);
      if ( v12 )
        return 0;
      result = RegDeleteKeyW(HKEY_CLASSES_ROOT, SubKey);
      v7 = result <= 0;
    }
    if ( !v7 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000277c  mov     [rsp-8+arg_0], rbx
0x180002781  mov     [rsp-8+arg_10], rsi
0x180002786  push    rbp
0x180002787  lea     rbp, [rsp-150h]
0x18000278f  sub     rsp, 250h
0x180002796  mov     rax, cs:__security_cookie
0x18000279d  xor     rax, rsp
0x1800027a0  mov     [rbp+150h+var_10], rax
0x1800027a7  lea     r8, [rbp+150h+SubKey]; unsigned __int16 *
0x1800027ab  call    ?GetMediaTypePath@@YAJPEBU_GUID@@0PEAGK@Z; GetMediaTypePath(_GUID const *,_GUID const *,ushort *,ulong)
0x1800027b0  test    eax, eax
0x1800027b2  js      loc_180002884
0x1800027b8  lea     rdx, [rbp+150h+SubKey]; lpSubKey
0x1800027bc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800027c3  call    cs:__imp_RegDeleteKeyW
0x1800027c9  test    eax, eax
0x1800027cb  jnz     loc_18000287A
0x1800027d1  lea     r8, [rbp+150h+SubKey]; unsigned __int16 *
0x1800027d5  xor     edx, edx; struct _GUID *
0x1800027d7  call    ?GetMediaTypePath@@YAJPEBU_GUID@@0PEAGK@Z; GetMediaTypePath(_GUID const *,_GUID const *,ushort *,ulong)
0x1800027dc  mov     [rsp+250h+var_220], eax
0x1800027e0  test    eax, eax
0x1800027e2  js      loc_180002884
0x1800027e8  lea     r9, [rsp+250h+var_220]; int *
0x1800027ed  lea     r8, [rbp+150h+SubKey]; unsigned __int16 *
0x1800027f1  lea     rcx, [rsp+250h+var_210]; this
0x1800027f6  call    ??0CKey@@QEAA@PEAUHKEY__@@PEBGPEAJHK@Z; CKey::CKey(HKEY__ *,ushort const *,long *,int,ulong)
0x1800027fb  cmp     [rsp+250h+var_220], 0
0x180002800  lea     rsi, ??_7CEnumKey@@6B@; const CEnumKey::`vftable'
0x180002807  mov     rdx, rsi
0x18000280a  mov     [rsp+250h+var_210], rdx
0x18000280f  jl      short loc_180002841
0x180002811  mov     eax, [rbp+150h+var_1B4]
0x180002814  inc     eax
0x180002816  cmp     eax, 1Eh
0x180002819  jbe     short loc_180002841
0x18000281b  mov     ecx, eax
0x18000281d  mov     eax, 2
0x180002822  mul     rcx
0x180002825  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000282c  cmovb   rax, rcx
0x180002830  mov     rcx, rax; unsigned __int64
0x180002833  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002838  mov     rdx, [rsp+250h+var_210]
0x18000283d  mov     [rbp+150h+var_1C0], rax
0x180002841  mov     rax, [rdx]
0x180002844  lea     rcx, [rsp+250h+var_210]
0x180002849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284e  lea     rcx, [rsp+250h+var_210]; this
0x180002853  mov     [rsp+250h+var_210], rsi
0x180002858  mov     ebx, eax
0x18000285a  call    ??1CKey@@QEAA@XZ; CKey::~CKey(void)
0x18000285f  test    ebx, ebx
0x180002861  jz      short loc_180002867
0x180002863  xor     eax, eax
0x180002865  jmp     short loc_180002884
0x180002867  lea     rdx, [rbp+150h+SubKey]; lpSubKey
0x18000286b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002872  call    cs:__imp_RegDeleteKeyW
0x180002878  test    eax, eax
0x18000287a  jle     short loc_180002884
0x18000287c  movzx   eax, ax
0x18000287f  or      eax, 80070000h
0x180002884  mov     rcx, [rbp+150h+var_10]
0x18000288b  xor     rcx, rsp; StackCookie
0x18000288e  call    __security_check_cookie
0x180002893  lea     r11, [rsp+250h+var_s0]
0x18000289b  mov     rbx, [r11+10h]
0x18000289f  mov     rsi, [r11+20h]
0x1800028a3  mov     rsp, r11
0x1800028a6  pop     rbp
0x1800028a7  retn
```
