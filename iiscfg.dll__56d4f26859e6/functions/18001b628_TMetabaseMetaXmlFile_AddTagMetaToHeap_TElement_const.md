# TMetabaseMetaXmlFile::AddTagMetaToHeap(TElement const &)

- ea: `0x18001b628`
- end: `0x18001b787`
- name: `?AddTagMetaToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@@Z`
- size: `351`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TElement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001c240`

## callees

- `0x18001b188`
- `0x18001b628`
- `0x18001c814`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!_wtol` at `0x18001b6c7`
- `msvcrt!_wtol` at `0x18001b701`
- `msvcrt!_wtol` at `0x18001b6c7`
- `msvcrt!_wtol` at `0x18001b701`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddTagMetaToHeap(TMetabaseMetaXmlFile *this, const struct TElement *a2)
{
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // rax
  TMetabaseMetaXmlFile *v5; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v6; // rax
  __int64 (__fastcall *v7)(TMetabaseMetaXmlFile *, _QWORD); // rdi
  TMetabaseMetaXmlFile *v8; // rcx
  const wchar_t *v9; // rcx
  unsigned int v10; // eax
  __int64 (__fastcall *v11)(TMetabaseMetaXmlFile *, _QWORD); // rdi
  TMetabaseMetaXmlFile *v12; // rcx
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rcx
  _DWORD v17[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v18; // [rsp+28h] [rbp-20h]

  v17[0] = *((_DWORD *)this + 636);
  v17[1] = *((_DWORD *)this + 634);
  v18 = 0;
  Attribute = TMetabaseMetaXmlFile::GetAttribute(this, a2, (TMetabaseMetaXmlFile *)((char *)this + 536));
  LODWORD(v18) = TMetabaseMetaXmlFile::AddStringToHeap(
                   this,
                   (const struct TMetabaseMetaXmlFile::TAttr *)((char *)Attribute + 16));
  v6 = TMetabaseMetaXmlFile::GetAttribute(v5, a2, (TMetabaseMetaXmlFile *)((char *)this + 664));
  DWORD1(v18) = TMetabaseMetaXmlFile::AddStringToHeap(
                  this,
                  (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v6 + 16));
  v7 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
  v9 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                      v8,
                                      a2,
                                      (TMetabaseMetaXmlFile *)((char *)this + 792))
                        + 3);
  if ( v9 )
    v10 = _wtol(v9);
  else
    v10 = 0;
  DWORD2(v18) = v7(this, v10);
  v11 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
  v13 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                       v12,
                                       a2,
                                       (TMetabaseMetaXmlFile *)((char *)this + 488))
                         + 3);
  if ( v13 )
    v14 = _wtol(v13);
  else
    v14 = 0;
  v15 = v11(this, v14);
  v16 = *(_QWORD *)this;
  HIDWORD(v18) = v15;
  if ( (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v16 + 152))(this, v15) > *((_DWORD *)this + 642) )
    *((_DWORD *)this + 642) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                                this,
                                HIDWORD(v18));
  (*(void (__fastcall **)(TMetabaseMetaXmlFile *, _DWORD *, __int64))(*(_QWORD *)this + 120LL))(this, v17, 1);
}

```

## disassembly

```asm
0x18001b628  mov     [rsp+arg_10], rbx
0x18001b62d  mov     [rsp+arg_18], rsi
0x18001b632  push    rdi
0x18001b633  sub     rsp, 40h
0x18001b637  mov     rax, cs:__security_cookie
0x18001b63e  xor     rax, rsp
0x18001b641  mov     [rsp+48h+var_10], rax
0x18001b646  mov     eax, [rcx+9F0h]
0x18001b64c  lea     r8, [rcx+218h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b653  mov     [rsp+48h+var_28], eax
0x18001b657  xorps   xmm0, xmm0
0x18001b65a  mov     eax, [rcx+9E8h]
0x18001b660  mov     rsi, rdx
0x18001b663  mov     [rsp+48h+var_24], eax
0x18001b667  mov     rbx, rcx
0x18001b66a  movdqu  [rsp+48h+var_20], xmm0
0x18001b670  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b675  mov     rcx, rbx; this
0x18001b678  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b67c  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b681  lea     r8, [rbx+298h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b688  mov     dword ptr [rsp+48h+var_20], eax
0x18001b68c  mov     rdx, rsi; struct TElement *
0x18001b68f  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b694  mov     rcx, rbx; this
0x18001b697  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b69b  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b6a0  mov     dword ptr [rsp+48h+var_20+4], eax
0x18001b6a4  lea     r8, [rbx+318h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b6ab  mov     rax, [rbx]
0x18001b6ae  mov     rdx, rsi; struct TElement *
0x18001b6b1  mov     rdi, [rax+10h]
0x18001b6b5  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b6ba  mov     rcx, [rax+18h]; String
0x18001b6be  test    rcx, rcx
0x18001b6c1  jnz     short loc_18001B6C7
0x18001b6c3  xor     eax, eax
0x18001b6c5  jmp     short loc_18001B6CD
0x18001b6c7  call    cs:__imp__wtol
0x18001b6cd  mov     edx, eax
0x18001b6cf  mov     rcx, rbx
0x18001b6d2  mov     rax, rdi
0x18001b6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6da  mov     dword ptr [rsp+48h+var_20+8], eax
0x18001b6de  lea     r8, [rbx+1E8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b6e5  mov     rax, [rbx]
0x18001b6e8  mov     rdx, rsi; struct TElement *
0x18001b6eb  mov     rdi, [rax+10h]
0x18001b6ef  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b6f4  mov     rcx, [rax+18h]; String
0x18001b6f8  test    rcx, rcx
0x18001b6fb  jnz     short loc_18001B701
0x18001b6fd  xor     eax, eax
0x18001b6ff  jmp     short loc_18001B707
0x18001b701  call    cs:__imp__wtol
0x18001b707  mov     edx, eax
0x18001b709  mov     rcx, rbx
0x18001b70c  mov     rax, rdi
0x18001b70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b714  mov     rcx, [rbx]
0x18001b717  mov     edx, eax
0x18001b719  mov     dword ptr [rsp+48h+var_20+0Ch], eax
0x18001b71d  mov     rax, [rcx+98h]
0x18001b724  mov     rcx, rbx
0x18001b727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b72c  cmp     eax, [rbx+0A08h]
0x18001b732  jbe     short loc_18001B750
0x18001b734  mov     rax, [rbx]
0x18001b737  mov     rcx, rbx
0x18001b73a  mov     edx, dword ptr [rsp+48h+var_20+0Ch]
0x18001b73e  mov     rax, [rax+98h]
0x18001b745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b74a  mov     [rbx+0A08h], eax
0x18001b750  mov     rax, [rbx]
0x18001b753  lea     rdx, [rsp+48h+var_28]
0x18001b758  mov     r8d, 1
0x18001b75e  mov     rcx, rbx
0x18001b761  mov     rax, [rax+78h]
0x18001b765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b76a  mov     rcx, [rsp+48h+var_10]
0x18001b76f  xor     rcx, rsp; StackCookie
0x18001b772  call    __security_check_cookie
0x18001b777  mov     rbx, [rsp+48h+arg_10]
0x18001b77c  mov     rsi, [rsp+48h+arg_18]
0x18001b781  add     rsp, 40h
0x18001b785  pop     rdi
0x18001b786  retn
```
