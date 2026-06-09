# FilestreamNtPath::InitializeNtPath(ushort const *)

- ea: `0x100544ad8`
- end: `0x100544eb7`
- name: `?InitializeNtPath@FilestreamNtPath@@QEAAJPEBG@Z`
- size: `991`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x100545070`

## callees

- `0x100544ad8`
- `0x100544ec0`
- `0x100544fa0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x100544b7f`
- `RPCRT4!UuidCreate` at `0x100544b7f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100544bfc`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100544bfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilestreamNtPath::InitializeNtPath(struct _UNICODE_STRING *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rax
  __int64 v7; // r15
  unsigned int v8; // eax
  int v9; // esi
  unsigned int v10; // ebx
  WCHAR *v11; // rax
  wchar_t *v12; // r8
  __int64 v13; // rdx
  __int64 Length; // rdx
  UUID *p_Uuid; // r10
  __int64 v16; // r11
  unsigned int v17; // ecx
  _QWORD v19[2]; // [rsp+30h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-48h] BYREF

  v19[1] = -2;
  v19[0] = -1;
  v4 = 0;
  if ( (bidGblFlags & 4) != 0 && off_1005E8328[0] )
    bidScopeEnterW(v19, off_1005E8328[0], a2);
  if ( !a2 )
    goto LABEL_48;
  v5 = 0x7FFF;
  v6 = a2;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = (0x7FFF - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
  {
LABEL_48:
    v10 = -1073741811;
    if ( (bidGblFlags & 2) == 0 || !off_1005E75F8[0] )
      goto LABEL_52;
    v12 = off_1005E75F8[0];
    v13 = 291840;
    goto LABEL_51;
  }
  v8 = UuidCreate(&Uuid);
  v9 = v8;
  if ( v8 && v8 != 1824 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E7600[0] )
      bidTraceW(0, 304128, off_1005E7600[0], v8);
    v10 = (unsigned __int16)v9 | 0xC0070000;
    if ( v9 <= 0 )
      v10 = v9;
    goto LABEL_52;
  }
  if ( !v7 || *a2 != 92 )
  {
    v10 = -1073741811;
    if ( (bidGblFlags & 2) == 0 || !off_1005E7608[0] )
      goto LABEL_52;
    v12 = off_1005E7608[0];
    v13 = 314368;
    goto LABEL_51;
  }
  v11 = (WCHAR *)malloc(2 * (v7 + 39));
  this->Buffer = v11;
  if ( !v11 )
  {
    v10 = -1073741801;
    if ( (bidGblFlags & 2) == 0 || !off_1005E7610[0] )
      goto LABEL_52;
    v12 = off_1005E7610[0];
    v13 = 344064;
LABEL_51:
    bidTraceW(0, v13, v12, v10);
LABEL_52:
    v4 = v10;
    goto LABEL_53;
  }
  this->Length = 0;
  this->MaximumLength = 2 * (v7 + 39);
  v10 = RtlUnicodeStringCchCopyStringN(this, FilestreamNtPath::PATH_PREFIX, 7u);
  if ( v10 )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E7618[0] )
      goto LABEL_52;
    v12 = off_1005E7618[0];
    v13 = 360448;
    goto LABEL_51;
  }
  v10 = RtlUnicodeStringCchCatStringN(this, a2 + 1, v7 - 1);
  if ( v10 )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E7620[0] )
      goto LABEL_52;
    v12 = off_1005E7620[0];
    v13 = 374784;
    goto LABEL_51;
  }
  v10 = RtlUnicodeStringCchCatStringN(this, FilestreamNtPath::PATH_SEPERATOR, 1u);
  if ( v10 )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E7628[0] )
      goto LABEL_52;
    v12 = off_1005E7628[0];
    v13 = 389120;
    goto LABEL_51;
  }
  Length = this->Length;
  if ( Length + 64 > (unsigned __int64)this->MaximumLength )
  {
    v10 = -2147483643;
    if ( (bidGblFlags & 2) == 0 || !off_1005E7630[0] )
      goto LABEL_52;
    v12 = off_1005E7630[0];
    v13 = 400384;
    goto LABEL_51;
  }
  p_Uuid = &Uuid;
  v16 = 16;
  do
  {
    this->Buffer[(unsigned __int64)(unsigned __int16)Length >> 1] = FilestreamNtPath::HEX_CHARS[(unsigned __int64)LOBYTE(p_Uuid->Data1) >> 4];
    v17 = (unsigned __int16)(this->Length + 2);
    this->Length = v17;
    this->Buffer[(unsigned __int64)v17 >> 1] = FilestreamNtPath::HEX_CHARS[p_Uuid->Data1 & 0xF];
    this->Length += 2;
    p_Uuid = (UUID *)((char *)p_Uuid + 1);
    LOWORD(Length) = this->Length;
    --v16;
  }
  while ( v16 );
  if ( (bidGblFlags & 2) != 0 && off_1005E7638[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
      bidID,
      0,
      427008,
      off_1005E7638[0],
      0);
LABEL_53:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v19);
  return v4;
}

```

## disassembly

```asm
0x100544ad8  mov     r11, rsp
0x100544adb  push    rsi
0x100544adc  push    rdi
0x100544add  push    r12
0x100544adf  push    r14
0x100544ae1  push    r15
0x100544ae3  sub     rsp, 60h
0x100544ae7  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x100544aef  mov     [r11+18h], rbx
0x100544af3  mov     [r11+20h], rbp
0x100544af7  mov     rax, cs:__security_cookie
0x100544afe  xor     rax, rsp
0x100544b01  mov     [rsp+88h+var_38], rax
0x100544b06  mov     rbp, rdx
0x100544b09  mov     r14, rcx
0x100544b0c  or      qword ptr [r11-58h], 0FFFFFFFFFFFFFFFFh
0x100544b11  xor     edi, edi
0x100544b13  test    byte ptr cs:_bidGblFlags, 4
0x100544b1a  jz      short loc_100544B3B
0x100544b1c  mov     rax, cs:off_1005E8328; "<FilestreamNtPath::InitializeNtPath>  '"...
0x100544b23  test    rax, rax
0x100544b26  jz      short loc_100544B3B
0x100544b28  mov     r8, rdx
0x100544b2b  mov     rdx, cs:off_1005E8328; "<FilestreamNtPath::InitializeNtPath>  '"...
0x100544b32  lea     rcx, [r11-58h]
0x100544b36  call    _bidScopeEnterW
0x100544b3b  mov     r12d, 2
0x100544b41  test    rbp, rbp
0x100544b44  jz      loc_100544E53
0x100544b4a  mov     edx, 7FFFh
0x100544b4f  mov     ecx, edx
0x100544b51  mov     rax, rbp
0x100544b54  cmp     [rax], di
0x100544b57  jz      short loc_100544B62
0x100544b59  add     rax, r12
0x100544b5c  sub     rcx, 1
0x100544b60  jnz     short loc_100544B54
0x100544b62  mov     rax, rcx
0x100544b65  sub     rdx, rcx
0x100544b68  neg     rax
0x100544b6b  sbb     r15, r15
0x100544b6e  and     r15, rdx
0x100544b71  test    rcx, rcx
0x100544b74  jz      loc_100544E53
0x100544b7a  lea     rcx, [rsp+88h+Uuid]; Uuid
0x100544b7f  call    cs:__imp_UuidCreate
0x100544b85  mov     esi, eax
0x100544b87  test    eax, eax
0x100544b89  jz      short loc_100544BDF
0x100544b8b  cmp     eax, 720h
0x100544b90  jz      short loc_100544BDF
0x100544b92  mov     ebp, 0C0070000h
0x100544b97  test    byte ptr cs:_bidGblFlags, r12b
0x100544b9e  jz      short loc_100544BD0
0x100544ba0  mov     rax, cs:off_1005E7600; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544ba7  test    rax, rax
0x100544baa  jz      short loc_100544BD0
0x100544bac  movzx   eax, si
0x100544baf  or      eax, ebp
0x100544bb1  test    esi, esi
0x100544bb3  cmovle  eax, esi
0x100544bb6  mov     dword ptr [rsp+88h+var_68], eax
0x100544bba  mov     r9d, esi
0x100544bbd  mov     r8, cs:off_1005E7600; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544bc4  mov     edx, 4A400h
0x100544bc9  xor     ecx, ecx
0x100544bcb  call    _bidTraceW
0x100544bd0  movzx   ebx, si
0x100544bd3  or      ebx, ebp
0x100544bd5  test    esi, esi
0x100544bd7  cmovle  ebx, esi
0x100544bda  jmp     loc_100544E83
0x100544bdf  cmp     r15, 1
0x100544be3  jb      loc_100544E2B
0x100544be9  cmp     word ptr [rbp+0], 5Ch ; '\'
0x100544bee  jnz     loc_100544E2B
0x100544bf4  lea     rbx, [r15+27h]
0x100544bf8  lea     rcx, [rbx+rbx]; Size
0x100544bfc  call    cs:__imp_malloc
0x100544c02  mov     [r14+8], rax
0x100544c06  test    rax, rax
0x100544c09  jnz     short loc_100544C3E
0x100544c0b  mov     ebx, 0C0000017h
0x100544c10  test    byte ptr cs:_bidGblFlags, r12b
0x100544c17  jz      loc_100544E83
0x100544c1d  mov     rax, cs:off_1005E7610; "<FilestreamNtPath::InitializeNtPath|MEM"...
0x100544c24  test    rax, rax
0x100544c27  jz      loc_100544E83
0x100544c2d  mov     r8, cs:off_1005E7610; "<FilestreamNtPath::InitializeNtPath|MEM"...
0x100544c34  mov     edx, 54000h
0x100544c39  jmp     loc_100544E79
0x100544c3e  mov     [r14], di
0x100544c42  add     bx, bx
0x100544c45  mov     [r14+2], bx
0x100544c4a  mov     r8d, 7; unsigned __int64
0x100544c50  mov     rdx, cs:?PATH_PREFIX@FilestreamNtPath@@2PEBGEB; unsigned __int16 *
0x100544c57  mov     rcx, r14; struct _UNICODE_STRING *
0x100544c5a  call    ?RtlUnicodeStringCchCopyStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCopyStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x100544c5f  mov     ebx, eax
0x100544c61  test    eax, eax
0x100544c63  jz      short loc_100544C93
0x100544c65  test    byte ptr cs:_bidGblFlags, r12b
0x100544c6c  jz      loc_100544E83
0x100544c72  mov     rax, cs:off_1005E7618; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544c79  test    rax, rax
0x100544c7c  jz      loc_100544E83
0x100544c82  mov     r8, cs:off_1005E7618; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544c89  mov     edx, 58000h
0x100544c8e  jmp     loc_100544E79
0x100544c93  lea     r8, [r15-1]; unsigned __int64
0x100544c97  lea     rdx, [rbp+2]; unsigned __int16 *
0x100544c9b  mov     rcx, r14; struct _UNICODE_STRING *
0x100544c9e  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x100544ca3  mov     ebx, eax
0x100544ca5  test    eax, eax
0x100544ca7  jz      short loc_100544CD7
0x100544ca9  test    byte ptr cs:_bidGblFlags, r12b
0x100544cb0  jz      loc_100544E83
0x100544cb6  mov     rax, cs:off_1005E7620; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544cbd  test    rax, rax
0x100544cc0  jz      loc_100544E83
0x100544cc6  mov     r8, cs:off_1005E7620; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544ccd  mov     edx, 5B800h
0x100544cd2  jmp     loc_100544E79
0x100544cd7  mov     r8d, 1; unsigned __int64
0x100544cdd  mov     rdx, cs:?PATH_SEPERATOR@FilestreamNtPath@@2PEBGEB; unsigned __int16 *
0x100544ce4  mov     rcx, r14; struct _UNICODE_STRING *
0x100544ce7  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x100544cec  mov     ebx, eax
0x100544cee  test    eax, eax
0x100544cf0  jz      short loc_100544D20
0x100544cf2  test    byte ptr cs:_bidGblFlags, r12b
0x100544cf9  jz      loc_100544E83
0x100544cff  mov     rax, cs:off_1005E7628; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544d06  test    rax, rax
0x100544d09  jz      loc_100544E83
0x100544d0f  mov     r8, cs:off_1005E7628; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544d16  mov     edx, 5F000h
0x100544d1b  jmp     loc_100544E79
0x100544d20  movzx   edx, word ptr [r14]
0x100544d24  lea     rcx, [rdx+40h]
0x100544d28  movzx   eax, word ptr [r14+2]
0x100544d2d  cmp     rcx, rax
0x100544d30  jbe     short loc_100544D65
0x100544d32  mov     ebx, 80000005h
0x100544d37  test    byte ptr cs:_bidGblFlags, r12b
0x100544d3e  jz      loc_100544E83
0x100544d44  mov     rax, cs:off_1005E7630; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544d4b  test    rax, rax
0x100544d4e  jz      loc_100544E83
0x100544d54  mov     r8, cs:off_1005E7630; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544d5b  mov     edx, 61C00h
0x100544d60  jmp     loc_100544E79
0x100544d65  lea     r10, [rsp+88h+Uuid]
0x100544d6a  mov     r11d, 10h
0x100544d70  movzx   ecx, byte ptr [r10]
0x100544d74  shr     rcx, 4
0x100544d78  movzx   r8d, dx
0x100544d7c  shr     r8, 1
0x100544d7f  mov     rdx, [r14+8]
0x100544d83  mov     rax, cs:?HEX_CHARS@FilestreamNtPath@@2PEBGEB; ushort const * const FilestreamNtPath::HEX_CHARS
0x100544d8a  movzx   ecx, word ptr [rax+rcx*2]
0x100544d8e  mov     [rdx+r8*2], cx
0x100544d93  movzx   eax, word ptr [r14]
0x100544d97  add     ax, r12w
0x100544d9b  movzx   ecx, ax
0x100544d9e  mov     [r14], cx
0x100544da2  movzx   r9d, byte ptr [r10]
0x100544da6  and     r9d, 0Fh
0x100544daa  mov     r8d, ecx
0x100544dad  shr     r8, 1
0x100544db0  mov     rdx, [r14+8]
0x100544db4  mov     rax, cs:?HEX_CHARS@FilestreamNtPath@@2PEBGEB; ushort const * const FilestreamNtPath::HEX_CHARS
0x100544dbb  movzx   ecx, word ptr [rax+r9*2]
0x100544dc0  mov     [rdx+r8*2], cx
0x100544dc5  add     [r14], r12w
0x100544dc9  inc     r10
0x100544dcc  movzx   edx, word ptr [r14]
0x100544dd0  sub     r11, 1
0x100544dd4  jnz     short loc_100544D70
0x100544dd6  test    byte ptr cs:_bidGblFlags, r12b
0x100544ddd  jz      loc_100544E85
0x100544de3  mov     rax, cs:off_1005E7638; "<FilestreamNtPath::InitializeNtPath|RET"...
0x100544dea  test    rax, rax
0x100544ded  jz      loc_100544E85
0x100544df3  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100544dfb  jz      loc_100544E85
0x100544e01  mov     rax, cs:off_1005D39E0
0x100544e08  mov     [rsp+88h+var_68], rdi
0x100544e0d  mov     r9, cs:off_1005E7638; "<FilestreamNtPath::InitializeNtPath|RET"...
0x100544e14  xor     edx, edx
0x100544e16  mov     r8d, 68400h
0x100544e1c  mov     rcx, cs:_bidID
0x100544e23  call    cs:__guard_dispatch_icall_fptr
0x100544e29  jmp     short loc_100544E85
0x100544e2b  mov     ebx, 0C000000Dh
0x100544e30  test    byte ptr cs:_bidGblFlags, r12b
0x100544e37  jz      short loc_100544E83
0x100544e39  mov     rax, cs:off_1005E7608; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544e40  test    rax, rax
0x100544e43  jz      short loc_100544E83
0x100544e45  mov     r8, cs:off_1005E7608; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544e4c  mov     edx, 4CC00h
0x100544e51  jmp     short loc_100544E79
0x100544e53  mov     ebx, 0C000000Dh
0x100544e58  test    byte ptr cs:_bidGblFlags, r12b
0x100544e5f  jz      short loc_100544E83
0x100544e61  mov     rax, cs:off_1005E75F8; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544e68  test    rax, rax
0x100544e6b  jz      short loc_100544E83
0x100544e6d  mov     r8, cs:off_1005E75F8; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x100544e74  mov     edx, 47400h
0x100544e79  mov     r9d, ebx
0x100544e7c  xor     ecx, ecx
0x100544e7e  call    _bidTraceW
0x100544e83  mov     edi, ebx
0x100544e85  lea     rcx, [rsp+88h+var_58]; this
0x100544e8a  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100544e8f  mov     eax, edi
0x100544e91  mov     rcx, [rsp+88h+var_38]
0x100544e96  xor     rcx, rsp; StackCookie
0x100544e99  call    __security_check_cookie
0x100544e9e  lea     r11, [rsp+88h+var_28]
0x100544ea3  mov     rbx, [r11+40h]
0x100544ea7  mov     rbp, [r11+48h]
0x100544eab  mov     rsp, r11
0x100544eae  pop     r15
0x100544eb0  pop     r14
0x100544eb2  pop     r12
0x100544eb4  pop     rdi
0x100544eb5  pop     rsi
0x100544eb6  retn
```
