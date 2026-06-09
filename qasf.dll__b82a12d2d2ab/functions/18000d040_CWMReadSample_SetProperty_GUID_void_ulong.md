# CWMReadSample::SetProperty(_GUID,void *,ulong)

- ea: `0x18000d040`
- end: `0x18000d111`
- name: `?SetProperty@CWMReadSample@@UEAAJU_GUID@@PEAXK@Z`
- size: `209`
- prototype: `int(CWMReadSample *__hidden this, struct _GUID *__struct_ptr, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001020`
- `0x180006f48`
- `0x18000d040`
- `0x1800131e0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMReadSample::SetProperty(CWMReadSample *this, __m128i *a2, void *a3, unsigned int a4)
{
  CBaseList *v4; // rsi
  __int64 i; // rcx
  __int64 v9; // r9
  CINSSBuffer3Attrib *v10; // rbx
  struct _GUID v11; // xmm0
  int v12; // edi
  struct _GUID v14; // [rsp+20h] [rbp-38h] BYREF

  v4 = (CWMReadSample *)((char *)this + 32);
  for ( i = *((_QWORD *)this + 4); i; i = *(_QWORD *)(i + 8) )
  {
    v9 = *(_QWORD *)(i + 16);
    if ( a2->m128i_i64[0] == *(_QWORD *)(v9 + 8) && _mm_srli_si128(*a2, 8).m128i_u64[0] == *(_QWORD *)(v9 + 16) )
      return (unsigned int)-2147467259;
  }
  v10 = (CINSSBuffer3Attrib *)operator new(0x30u);
  if ( v10 )
  {
    v11 = (struct _GUID)*a2;
    *((_QWORD *)v10 + 3) = 0;
    *(_QWORD *)v10 = &CINSSBuffer3Attrib::`vftable';
    *((_QWORD *)v10 + 4) = 0;
    v14 = v11;
    v12 = CINSSBuffer3Attrib::SetAttributeData(v10, &v14, a3, a4);
    if ( v12 < 0 )
      (**(void (__fastcall ***)(CINSSBuffer3Attrib *, __int64))v10)(v10, 1);
    else
      CBaseList::AddTailI(v4, v10);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d040  push    rbx
0x18000d042  push    rbp
0x18000d043  push    rsi
0x18000d044  push    rdi
0x18000d045  push    r14
0x18000d047  sub     rsp, 30h
0x18000d04b  lea     rsi, [rcx+20h]
0x18000d04f  mov     ebp, r9d
0x18000d052  mov     rcx, [rsi]
0x18000d055  mov     r14, r8
0x18000d058  mov     rdi, rdx
0x18000d05b  jmp     short loc_18000D083
0x18000d05d  movups  xmm0, xmmword ptr [rdx]
0x18000d060  mov     r9, [rcx+10h]
0x18000d064  movq    rax, xmm0
0x18000d069  cmp     rax, [r9+8]
0x18000d06d  jnz     short loc_18000D07F
0x18000d06f  psrldq  xmm0, 8
0x18000d074  movq    rax, xmm0
0x18000d079  cmp     rax, [r9+10h]
0x18000d07d  jz      short loc_18000D0E3
0x18000d07f  mov     rcx, [rcx+8]
0x18000d083  test    rcx, rcx
0x18000d086  jnz     short loc_18000D05D
0x18000d088  mov     ecx, 30h ; '0'; Size
0x18000d08d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d092  mov     rbx, rax
0x18000d095  test    rax, rax
0x18000d098  jz      short loc_18000D0FF
0x18000d09a  movups  xmm0, xmmword ptr [rdi]
0x18000d09d  lea     rax, ??_7CINSSBuffer3Attrib@@6B@; const CINSSBuffer3Attrib::`vftable'
0x18000d0a4  mov     qword ptr [rbx+18h], 0
0x18000d0ac  mov     r9d, ebp; unsigned int
0x18000d0af  mov     [rbx], rax
0x18000d0b2  mov     r8, r14; void *
0x18000d0b5  mov     qword ptr [rbx+20h], 0
0x18000d0bd  lea     rdx, [rsp+58h+var_38]; struct _GUID
0x18000d0c2  mov     rcx, rbx; this
0x18000d0c5  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x18000d0cb  call    ?SetAttributeData@CINSSBuffer3Attrib@@QEAAJU_GUID@@PEAXK@Z; CINSSBuffer3Attrib::SetAttributeData(_GUID,void *,ulong)
0x18000d0d0  mov     edi, eax
0x18000d0d2  test    eax, eax
0x18000d0d4  js      short loc_18000D0EA
0x18000d0d6  mov     rdx, rbx; void *
0x18000d0d9  mov     rcx, rsi; this
0x18000d0dc  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000d0e1  jmp     short loc_18000D104
0x18000d0e3  mov     edi, 80004005h
0x18000d0e8  jmp     short loc_18000D104
0x18000d0ea  mov     rax, [rbx]
0x18000d0ed  mov     edx, 1
0x18000d0f2  mov     rcx, rbx
0x18000d0f5  mov     rax, [rax]
0x18000d0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0fd  jmp     short loc_18000D104
0x18000d0ff  mov     edi, 8007000Eh
0x18000d104  mov     eax, edi
0x18000d106  add     rsp, 30h
0x18000d10a  pop     r14
0x18000d10c  pop     rdi
0x18000d10d  pop     rsi
0x18000d10e  pop     rbp
0x18000d10f  pop     rbx
0x18000d110  retn
```
