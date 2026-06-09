# CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)

- ea: `0x18002db80`
- end: `0x18002dcfc`
- name: `?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z`
- size: `380`
- prototype: `int(CWriter *__hidden this, const unsigned __int16 *, struct CWriterGlobalHelper *, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009c14`
- `0x1800120b4`
- `0x180023df4`
- `0x180024e90`

## callees

- `0x1800089c8`
- `0x18002da58`
- `0x18002db80`
- `0x180031010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002dbea`
- `msvcrt!wcscpy_s` at `0x18002dbea`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002dc38`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002dc38`

## pseudocode

```c
__int64 __fastcall CWriter::Initialize(
        CWriter *this,
        const unsigned __int16 *a2,
        struct CWriterGlobalHelper *a3,
        void *a4)
{
  __int64 v6; // rax
  rsize_t v9; // rbp
  wchar_t *v10; // rax
  int GlobalHelper; // ebx
  _QWORD v13[9]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+8h] BYREF

  v13[0] = 0;
  v14 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v9 = v6 + 1;
  v10 = (wchar_t *)operator new(saturated_mul(v6 + 1, 2u));
  *(_QWORD *)this = v10;
  if ( !v10 )
  {
    GlobalHelper = -2147024882;
    goto LABEL_11;
  }
  wcscpy_s(v10, v9, a2);
  *((_QWORD *)this + 8199) = a4;
  *((_QWORD *)this + 8200) = a3;
  *((_DWORD *)this + 4) = 0;
  if ( !a3 )
  {
    GlobalHelper = GetGlobalHelper(0, (struct CWriterGlobalHelper **)this + 8200);
    if ( GlobalHelper < 0 )
      goto LABEL_11;
    *((_DWORD *)this + 3) = 1;
  }
  GlobalHelper = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, v13, L"IIS");
  if ( GlobalHelper >= 0 )
  {
    GlobalHelper = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v13[0])(
                     v13[0],
                     &IID_IAdvancedTableDispenser,
                     &v14);
    if ( GlobalHelper >= 0 )
      GlobalHelper = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, int, int, char *))(*(_QWORD *)v14 + 32LL))(
                       v14,
                       L"METABASE",
                       L"MBProperty",
                       0,
                       0,
                       0,
                       3,
                       2,
                       (char *)this + 65608);
  }
LABEL_11:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
  return (unsigned int)GlobalHelper;
}

```

## disassembly

```asm
0x18002db80  mov     rax, rsp
0x18002db83  push    rbx
0x18002db84  push    rbp
0x18002db85  push    rsi
0x18002db86  push    rdi
0x18002db87  push    r14
0x18002db89  push    r15
0x18002db8b  sub     rsp, 68h
0x18002db8f  xor     r15d, r15d
0x18002db92  mov     rdi, rcx
0x18002db95  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002db99  mov     [rax-48h], r15
0x18002db9d  mov     [rax+8], r15
0x18002dba1  mov     r14, r9
0x18002dba4  mov     rax, rcx
0x18002dba7  mov     rsi, r8
0x18002dbaa  mov     rbx, rdx
0x18002dbad  inc     rax
0x18002dbb0  cmp     [rdx+rax*2], r15w
0x18002dbb5  jnz     short loc_18002DBAD
0x18002dbb7  lea     rbp, [rax+1]
0x18002dbbb  mov     eax, 2
0x18002dbc0  mul     rbp
0x18002dbc3  cmovb   rax, rcx
0x18002dbc7  mov     rcx, rax; Size
0x18002dbca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dbcf  mov     [rdi], rax
0x18002dbd2  test    rax, rax
0x18002dbd5  jnz     short loc_18002DBE1
0x18002dbd7  mov     ebx, 8007000Eh
0x18002dbdc  jmp     loc_18002DCB6
0x18002dbe1  mov     r8, rbx; Source
0x18002dbe4  mov     rdx, rbp; SizeInWords
0x18002dbe7  mov     rcx, rax; Destination
0x18002dbea  call    cs:__imp_wcscpy_s
0x18002dbf0  mov     [rdi+10038h], r14
0x18002dbf7  lea     rdx, [rdi+10040h]; struct CWriterGlobalHelper **
0x18002dbfe  mov     [rdx], rsi
0x18002dc01  mov     ebp, 1
0x18002dc06  mov     [rdi+10h], r15d
0x18002dc0a  test    rsi, rsi
0x18002dc0d  jnz     short loc_18002DC23
0x18002dc0f  xor     ecx, ecx; int
0x18002dc11  call    ?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z; GetGlobalHelper(int,CWriterGlobalHelper * *)
0x18002dc16  mov     ebx, eax
0x18002dc18  test    eax, eax
0x18002dc1a  js      loc_18002DCB6
0x18002dc20  mov     [rdi+0Ch], ebp
0x18002dc23  lea     r9, aIis; "IIS"
0x18002dc2a  mov     ecx, ebp
0x18002dc2c  lea     r8, [rsp+98h+var_48]
0x18002dc31  lea     rdx, IID_ISimpleTableDispenser2
0x18002dc38  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18002dc3e  mov     ebx, eax
0x18002dc40  test    eax, eax
0x18002dc42  js      short loc_18002DCB6
0x18002dc44  mov     rcx, [rsp+98h+var_48]
0x18002dc49  lea     r8, [rsp+98h+arg_0]
0x18002dc51  lea     rdx, IID_IAdvancedTableDispenser
0x18002dc58  mov     rax, [rcx]
0x18002dc5b  mov     rax, [rax]
0x18002dc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc63  mov     ebx, eax
0x18002dc65  test    eax, eax
0x18002dc67  js      short loc_18002DCB6
0x18002dc69  mov     rcx, [rsp+98h+arg_0]
0x18002dc71  lea     rdx, [rdi+10048h]
0x18002dc78  mov     [rsp+98h+var_58], rdx
0x18002dc7d  lea     r8, aMbproperty_0; "MBProperty"
0x18002dc84  mov     [rsp+98h+var_60], 2
0x18002dc8c  lea     rdx, aMetabase; "METABASE"
0x18002dc93  mov     [rsp+98h+var_68], 3
0x18002dc9b  xor     r9d, r9d
0x18002dc9e  mov     rax, [rcx]
0x18002dca1  mov     [rsp+98h+var_70], r15
0x18002dca6  mov     [rsp+98h+var_78], r15
0x18002dcab  mov     rax, [rax+20h]
0x18002dcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcb4  mov     ebx, eax
0x18002dcb6  mov     rcx, [rsp+98h+arg_0]
0x18002dcbe  test    rcx, rcx
0x18002dcc1  jz      short loc_18002DCD7
0x18002dcc3  mov     rax, [rcx]
0x18002dcc6  mov     rax, [rax+10h]
0x18002dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dccf  mov     [rsp+98h+arg_0], r15
0x18002dcd7  mov     rcx, [rsp+98h+var_48]
0x18002dcdc  test    rcx, rcx
0x18002dcdf  jz      short loc_18002DCED
0x18002dce1  mov     rax, [rcx]
0x18002dce4  mov     rax, [rax+10h]
0x18002dce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dced  mov     eax, ebx
0x18002dcef  add     rsp, 68h
0x18002dcf3  pop     r15
0x18002dcf5  pop     r14
0x18002dcf7  pop     rdi
0x18002dcf8  pop     rsi
0x18002dcf9  pop     rbp
0x18002dcfa  pop     rbx
0x18002dcfb  retn
```
