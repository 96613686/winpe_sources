# CScrub::_GetFullPathName(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x180027858`
- end: `0x180027a04`
- name: `?_GetFullPathName@CScrub@@AEAAPEBU_UNICODE_STRING@@PEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU2@2@Z`
- size: `428`
- prototype: `const struct _UNICODE_STRING *__fastcall(CScrub *this, struct _SCRUB_THREAD_CONTEXT *, struct CFileName *, const struct _UNICODE_STRING *)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1800273d8`
- `0x180027b88`
- `0x180028360`
- `0x18002892c`
- `0x1800293d4`
- `0x1800299f0`
- `0x18002a2e0`

## callees

- `0x18000f478`
- `0x18000f554`
- `0x180012158`
- `0x180021c80`
- `0x180027160`
- `0x180027858`

## pseudocode

```c
const struct _UNICODE_STRING *__fastcall CScrub::_GetFullPathName(
        CScrub *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        struct CFileName *a3,
        const struct _UNICODE_STRING *a4)
{
  _QWORD *v4; // r14
  struct _UNICODE_STRING *v5; // rdi
  int FullPath; // eax
  __int64 v10; // r8
  _QWORD *v11; // rcx
  int v12; // edx
  unsigned __int16 Length; // bx
  int v14; // eax
  int v15; // eax
  unsigned __int16 v17; // [rsp+88h] [rbp+10h] BYREF

  v4 = (_QWORD *)((char *)a2 + 34456);
  v5 = (struct _UNICODE_STRING *)((char *)a2 + 34440);
  FullPath = CFileName::GetFullPath(a3, (char *)a2 + 34440, (char *)a2 + 34456);
  v10 = (unsigned int)FullPath;
  if ( FullPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v12 = 180;
    goto LABEL_17;
  }
  Length = v5->Length;
  v17 = v5->Length;
  if ( a4 )
  {
    v14 = UShortAdd(Length, 2u, &v17);
    LOBYTE(v10) = v14;
    if ( v14 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v12 = 181;
      goto LABEL_17;
    }
    v15 = UShortAdd(v17, a4->Length, &v17);
    v10 = (unsigned int)v15;
    if ( v15 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v12 = 182;
LABEL_17:
      WPP_SF_DDZd(
        v11[2],
        v12,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v10);
      return 0;
    }
    Length = v17;
  }
  if ( *((_WORD *)a2 + 17221) < Length )
  {
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CCRTAllocator>::ReallocateBytes(v4, Length, v10) )
      return 0;
    *((_QWORD *)a2 + 4306) = *v4;
    *((_WORD *)a2 + 17221) = Length;
  }
  if ( a4 )
  {
    RtlUnicodeStringCat(v5, &BackslashString);
    RtlUnicodeStringCat(v5, a4);
  }
  return v5;
}

```

## disassembly

```asm
0x180027858  push    rbx
0x18002785a  push    rbp
0x18002785b  push    rsi
0x18002785c  push    rdi
0x18002785d  push    r14
0x18002785f  push    r15
0x180027861  sub     rsp, 48h
0x180027865  mov     rax, r8
0x180027868  lea     r14, [rdx+8698h]
0x18002786f  lea     rdi, [rdx+8688h]
0x180027876  mov     rbp, rdx
0x180027879  mov     r15, rcx
0x18002787c  mov     r8, r14
0x18002787f  mov     rdx, rdi
0x180027882  mov     rcx, rax
0x180027885  mov     rsi, r9
0x180027888  call    ?GetFullPath@CFileName@@QEAAJPEAU_UNICODE_STRING@@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z; CFileName::GetFullPath(_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)
0x18002788d  mov     r8d, eax
0x180027890  test    eax, eax
0x180027892  jns     short loc_1800278C9
0x180027894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002789b  lea     rax, WPP_GLOBAL_Control
0x1800278a2  cmp     rcx, rax
0x1800278a5  jz      loc_1800279C0
0x1800278ab  test    byte ptr [rcx+1Ch], 1
0x1800278af  jz      loc_1800279C0
0x1800278b5  cmp     byte ptr [rcx+19h], 2
0x1800278b9  jb      loc_1800279C0
0x1800278bf  mov     edx, 0B4h
0x1800278c4  jmp     loc_18002796E
0x1800278c9  movzx   ebx, word ptr [rdi]
0x1800278cc  mov     [rsp+78h+arg_8], bx
0x1800278d4  test    rsi, rsi
0x1800278d7  jz      loc_1800279A8
0x1800278dd  mov     edx, 2; unsigned __int16
0x1800278e2  lea     r8, [rsp+78h+arg_8]; unsigned __int16 *
0x1800278ea  movzx   ecx, bx; unsigned __int16
0x1800278ed  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x1800278f2  mov     r8d, eax
0x1800278f5  test    eax, eax
0x1800278f7  jns     short loc_18002792B
0x1800278f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027900  lea     rax, WPP_GLOBAL_Control
0x180027907  cmp     rcx, rax
0x18002790a  jz      loc_1800279C0
0x180027910  test    byte ptr [rcx+1Ch], 1
0x180027914  jz      loc_1800279C0
0x18002791a  cmp     byte ptr [rcx+19h], 2
0x18002791e  jb      loc_1800279C0
0x180027924  mov     edx, 0B5h
0x180027929  jmp     short loc_18002796E
0x18002792b  movzx   edx, word ptr [rsi]; unsigned __int16
0x18002792e  lea     r8, [rsp+78h+arg_8]; unsigned __int16 *
0x180027936  movzx   ecx, [rsp+78h+arg_8]; unsigned __int16
0x18002793e  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x180027943  mov     r8d, eax
0x180027946  test    eax, eax
0x180027948  jns     short loc_1800279A0
0x18002794a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027951  lea     rax, WPP_GLOBAL_Control
0x180027958  cmp     rcx, rax
0x18002795b  jz      short loc_1800279C0
0x18002795d  test    byte ptr [rcx+1Ch], 1
0x180027961  jz      short loc_1800279C0
0x180027963  cmp     byte ptr [rcx+19h], 2
0x180027967  jb      short loc_1800279C0
0x180027969  mov     edx, 0B6h
0x18002796e  mov     rax, [r15]
0x180027971  mov     rcx, [rcx+10h]
0x180027975  mov     [rsp+78h+var_48], r8d
0x18002797a  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180027981  mov     r9, [rax]
0x180027984  mov     rax, [rax+40h]
0x180027988  mov     [rsp+78h+var_50], rax
0x18002798d  mov     eax, [r9+24h]
0x180027991  mov     r9d, [r9+10h]
0x180027995  mov     [rsp+78h+var_58], eax
0x180027999  call    WPP_SF_DDZd
0x18002799e  jmp     short loc_1800279C0
0x1800279a0  movzx   ebx, [rsp+78h+arg_8]
0x1800279a8  cmp     [rbp+868Ah], bx
0x1800279af  jnb     short loc_1800279D5
0x1800279b1  movzx   edx, bx
0x1800279b4  mov     rcx, r14
0x1800279b7  call    ?ReallocateBytes@?$CHeapPtrBase@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CCRTAllocator>::ReallocateBytes(unsigned __int64)
0x1800279bc  test    al, al
0x1800279be  jnz     short loc_1800279C4
0x1800279c0  xor     eax, eax
0x1800279c2  jmp     short loc_1800279F7
0x1800279c4  mov     rax, [r14]
0x1800279c7  mov     [rbp+8690h], rax
0x1800279ce  mov     [rbp+868Ah], bx
0x1800279d5  test    rsi, rsi
0x1800279d8  jz      short loc_1800279F4
0x1800279da  lea     rdx, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800279e1  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800279e4  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x1800279e9  mov     rdx, rsi; struct _UNICODE_STRING *
0x1800279ec  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800279ef  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x1800279f4  mov     rax, rdi
0x1800279f7  add     rsp, 48h
0x1800279fb  pop     r15
0x1800279fd  pop     r14
0x1800279ff  pop     rdi
0x180027a00  pop     rsi
0x180027a01  pop     rbp
0x180027a02  pop     rbx
0x180027a03  retn
```
