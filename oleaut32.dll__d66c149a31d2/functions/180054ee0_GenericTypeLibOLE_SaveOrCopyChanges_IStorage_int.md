# GenericTypeLibOLE::SaveOrCopyChanges(IStorage *,int)

- ea: `0x180054ee0`
- end: `0x180055042`
- name: `?SaveOrCopyChanges@GenericTypeLibOLE@@QEAAJPEAUIStorage@@H@Z`
- size: `354`
- prototype: `__int64 __fastcall(GenericTypeLibOLE *__hidden this, struct IStorage *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054d00`
- `0x180054d10`

## callees

- `0x18004b970`
- `0x18004e87c`
- `0x1800535c0`
- `0x180054ee0`
- `0x180055348`
- `0x180056004`
- `0x18009c010`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!WriteStorageProperties` at `0x18005501d`
- `ext-ms-win-ole32-oleautomation-l1-1-0!WriteStorageProperties` at `0x18005501d`

## pseudocode

```c
__int64 __fastcall GenericTypeLibOLE::SaveOrCopyChanges(GenericTypeLibOLE *this, struct IStorage *a2)
{
  __int64 result; // rax
  __int64 v5; // rcx
  unsigned int i; // esi
  __int64 v7; // rax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  int v10; // ebx
  struct STREAM *v11; // rsi
  int v12; // eax
  struct STREAM *v13; // [rsp+48h] [rbp+20h] BYREF

  v13 = 0;
  result = GenericTypeLibOLE::GetTypeComp(this, (struct ITypeComp **)&v13);
  if ( (int)result < 0 )
    return result;
  (*(void (__fastcall **)(struct STREAM *))(*(_QWORD *)v13 + 16LL))(v13);
  v5 = *((_QWORD *)this + 18);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_QWORD *)this + 18) = a2;
  for ( i = 0; i < *((unsigned __int16 *)this + 120); ++i )
  {
    v7 = *((_QWORD *)this + 4);
    v8 = *(_QWORD *)(v7 + 80LL * (unsigned __int16)i + 8);
    v9 = *(_DWORD **)(v8 + 48);
    if ( !v9 )
    {
      if ( !v8 )
        continue;
      v9 = *(_DWORD **)(v7 + 80LL * (unsigned __int16)i + 8);
    }
    if ( v9[4] )
    {
      v10 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 208LL))(v9);
      if ( v10 )
        goto LABEL_21;
    }
  }
  v13 = 0;
  v10 = GenericTypeLibOLE::OpenTypeStream(this, 0xFFFFFFFFLL, 1, &v13);
  if ( v10 >= 0 )
  {
    v11 = v13;
    v10 = GenericTypeLibOLE::Write(this, v13);
    if ( !v10 )
      v10 = GenericTypeLibOLE::SetModified(this, 0);
    v12 = (*(__int64 (__fastcall **)(struct STREAM *))(*(_QWORD *)v11 + 40LL))(v11);
    if ( !v10 )
      v10 = v12;
  }
  if ( v10 >= 0 )
  {
    if ( (unsigned __int8)IsMonikerLoadTypeLibPresent() )
      v10 = WriteStorageProperties(*((_QWORD *)this + 18), &CLSID_GenericTypeLibOLE, 512, L"TYPELIB");
    else
      v10 = -2147467263;
  }
LABEL_21:
  *((_QWORD *)this + 18) = 0;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180054ee0  mov     rax, rsp
0x180054ee3  mov     [rax+8], rbx
0x180054ee7  mov     [rax+10h], rsi
0x180054eeb  push    rdi
0x180054eec  sub     rsp, 20h
0x180054ef0  mov     rbx, rdx
0x180054ef3  mov     qword ptr [rax+20h], 0
0x180054efb  lea     rdx, [rax+20h]; struct ITypeComp **
0x180054eff  mov     rdi, rcx
0x180054f02  call    ?GetTypeComp@GenericTypeLibOLE@@UEAAJPEAPEAUITypeComp@@@Z; GenericTypeLibOLE::GetTypeComp(ITypeComp * *)
0x180054f07  test    eax, eax
0x180054f09  js      loc_180055032
0x180054f0f  mov     rcx, [rsp+28h+arg_18]
0x180054f14  mov     rax, [rcx]
0x180054f17  mov     rax, [rax+10h]
0x180054f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f20  mov     rcx, [rdi+90h]
0x180054f27  test    rcx, rcx
0x180054f2a  jz      short loc_180054F38
0x180054f2c  mov     rax, [rcx]
0x180054f2f  mov     rax, [rax+10h]
0x180054f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f38  mov     [rdi+90h], rbx
0x180054f3f  xor     esi, esi
0x180054f41  movzx   eax, word ptr [rdi+0F0h]
0x180054f48  cmp     esi, eax
0x180054f4a  jnb     short loc_180054F93
0x180054f4c  movzx   eax, si
0x180054f4f  lea     rcx, [rax+rax*4]
0x180054f53  mov     rax, [rdi+20h]
0x180054f57  add     rcx, rcx
0x180054f5a  mov     rdx, [rax+rcx*8+8]
0x180054f5f  mov     rcx, [rdx+30h]
0x180054f63  test    rcx, rcx
0x180054f66  jnz     short loc_180054F70
0x180054f68  test    rdx, rdx
0x180054f6b  jz      short loc_180054F8F
0x180054f6d  mov     rcx, rdx
0x180054f70  cmp     dword ptr [rcx+10h], 0
0x180054f74  jz      short loc_180054F8F
0x180054f76  mov     rax, [rcx]
0x180054f79  mov     rax, [rax+0D0h]
0x180054f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f85  mov     ebx, eax
0x180054f87  test    eax, eax
0x180054f89  jnz     loc_180055025
0x180054f8f  inc     esi
0x180054f91  jmp     short loc_180054F41
0x180054f93  lea     r9, [rsp+28h+arg_18]
0x180054f98  mov     [rsp+28h+arg_18], 0
0x180054fa1  mov     r8d, 1
0x180054fa7  or      edx, 0FFFFFFFFh
0x180054faa  mov     rcx, rdi
0x180054fad  call    ?OpenTypeStream@GenericTypeLibOLE@@QEAAJIW4STREAM_OPEN_MODE@@PEAPEAVSTREAM@@@Z; GenericTypeLibOLE::OpenTypeStream(uint,STREAM_OPEN_MODE,STREAM * *)
0x180054fb2  mov     ebx, eax
0x180054fb4  test    eax, eax
0x180054fb6  js      short loc_180054FEE
0x180054fb8  mov     rsi, [rsp+28h+arg_18]
0x180054fbd  mov     rcx, rdi; this
0x180054fc0  mov     rdx, rsi; struct STREAM *
0x180054fc3  call    ?Write@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@@Z; GenericTypeLibOLE::Write(STREAM *)
0x180054fc8  mov     ebx, eax
0x180054fca  test    eax, eax
0x180054fcc  jnz     short loc_180054FDA
0x180054fce  xor     edx, edx; int
0x180054fd0  mov     rcx, rdi; this
0x180054fd3  call    ?SetModified@GenericTypeLibOLE@@QEAAJH@Z; GenericTypeLibOLE::SetModified(int)
0x180054fd8  mov     ebx, eax
0x180054fda  mov     rax, [rsi]
0x180054fdd  mov     rcx, rsi
0x180054fe0  mov     rax, [rax+28h]
0x180054fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fe9  test    ebx, ebx
0x180054feb  cmovz   ebx, eax
0x180054fee  test    ebx, ebx
0x180054ff0  js      short loc_180055025
0x180054ff2  call    IsMonikerLoadTypeLibPresent
0x180054ff7  test    al, al
0x180054ff9  jnz     short loc_180055002
0x180054ffb  mov     ebx, 80004001h
0x180055000  jmp     short loc_180055025
0x180055002  mov     rcx, [rdi+90h]
0x180055009  lea     r9, aTypelib; "TYPELIB"
0x180055010  mov     r8d, 200h
0x180055016  lea     rdx, CLSID_GenericTypeLibOLE
0x18005501d  call    cs:__imp_WriteStorageProperties
0x180055023  mov     ebx, eax
0x180055025  mov     qword ptr [rdi+90h], 0
0x180055030  mov     eax, ebx
0x180055032  mov     rbx, [rsp+28h+arg_0]
0x180055037  mov     rsi, [rsp+28h+arg_8]
0x18005503c  add     rsp, 20h
0x180055040  pop     rdi
0x180055041  retn
```
