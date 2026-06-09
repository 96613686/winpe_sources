# CWMWriter::DeletePins(int)

- ea: `0x18000f594`
- end: `0x18000f6a6`
- name: `?DeletePins@CWMWriter@@QEAAXH@Z`
- size: `274`
- prototype: `void __fastcall(CWMWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e238`
- `0x18000ea00`

## callees

- `0x180006f48`
- `0x180007004`
- `0x180007210`
- `0x18000f594`
- `0x18001f010`

## pseudocode

```c
void __fastcall CWMWriter::DeletePins(CWMWriter *this, int a2)
{
  CBaseList *v3; // r14
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rsi

  v3 = (CWMWriter *)((char *)this + 408);
  while ( 1 )
  {
    v7 = CBaseList::RemoveI(v3, *(struct __POSITION **)v3);
    v8 = v7;
    if ( !v7 )
      break;
    --*((_DWORD *)this + 122);
    v5 = *(_DWORD *)(v7 + 424);
    switch ( v5 )
    {
      case 1:
        --*((_DWORD *)this + 123);
        break;
      case 2:
        --*((_DWORD *)this + 124);
        break;
      case 3:
        --*((_DWORD *)this + 125);
        break;
      case 4:
        --*((_DWORD *)this + 126);
        break;
      case 6:
        --*((_DWORD *)this + 127);
        break;
      case 5:
        --*((_DWORD *)this + 128);
        break;
    }
    FreeMediaType((struct _AMMediaType *)(v8 + 104));
    v6 = *(_QWORD *)(v8 + 448);
    *(GUID *)(v8 + 104) = GUID_NULL;
    *(GUID *)(v8 + 120) = GUID_NULL;
    *(GUID *)(v8 + 148) = GUID_NULL;
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *(_QWORD *)(v8 + 448) = 0;
    }
    if ( a2 )
      CBaseList::AddTailI((CWMWriter *)((char *)this + 448), (void *)v8);
    else
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
  }
}

```

## disassembly

```asm
0x18000f594  push    rbx
0x18000f596  push    rbp
0x18000f597  push    rsi
0x18000f598  push    rdi
0x18000f599  push    r14
0x18000f59b  sub     rsp, 20h
0x18000f59f  mov     ebp, edx
0x18000f5a1  lea     r14, [rcx+198h]
0x18000f5a8  mov     rdi, rcx
0x18000f5ab  jmp     loc_18000F684
0x18000f5b0  dec     dword ptr [rdi+1E8h]
0x18000f5b6  mov     eax, [rsi+1A8h]
0x18000f5bc  cmp     eax, 1
0x18000f5bf  jnz     short loc_18000F5C9
0x18000f5c1  dec     dword ptr [rdi+1ECh]
0x18000f5c7  jmp     short loc_18000F608
0x18000f5c9  cmp     eax, 2
0x18000f5cc  jnz     short loc_18000F5D6
0x18000f5ce  dec     dword ptr [rdi+1F0h]
0x18000f5d4  jmp     short loc_18000F608
0x18000f5d6  cmp     eax, 3
0x18000f5d9  jnz     short loc_18000F5E3
0x18000f5db  dec     dword ptr [rdi+1F4h]
0x18000f5e1  jmp     short loc_18000F608
0x18000f5e3  cmp     eax, 4
0x18000f5e6  jnz     short loc_18000F5F0
0x18000f5e8  dec     dword ptr [rdi+1F8h]
0x18000f5ee  jmp     short loc_18000F608
0x18000f5f0  cmp     eax, 6
0x18000f5f3  jnz     short loc_18000F5FD
0x18000f5f5  dec     dword ptr [rdi+1FCh]
0x18000f5fb  jmp     short loc_18000F608
0x18000f5fd  cmp     eax, 5
0x18000f600  jnz     short loc_18000F608
0x18000f602  dec     dword ptr [rdi+200h]
0x18000f608  lea     rcx, [rsi+68h]; struct _AMMediaType *
0x18000f60c  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000f611  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f618  mov     rcx, [rsi+1C0h]
0x18000f61f  movdqu  xmmword ptr [rsi+68h], xmm0
0x18000f624  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000f62b  movdqu  xmmword ptr [rsi+78h], xmm1
0x18000f630  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f637  movdqu  xmmword ptr [rsi+94h], xmm0
0x18000f63f  test    rcx, rcx
0x18000f642  jz      short loc_18000F65B
0x18000f644  mov     rax, [rcx]
0x18000f647  mov     rax, [rax+10h]
0x18000f64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f650  mov     qword ptr [rsi+1C0h], 0
0x18000f65b  test    ebp, ebp
0x18000f65d  jz      short loc_18000F670
0x18000f65f  lea     rcx, [rdi+1C0h]; this
0x18000f666  mov     rdx, rsi; void *
0x18000f669  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000f66e  jmp     short loc_18000F684
0x18000f670  mov     rax, [rsi]
0x18000f673  mov     edx, 1
0x18000f678  mov     rcx, rsi
0x18000f67b  mov     rax, [rax+18h]
0x18000f67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f684  mov     rdx, [r14]; struct __POSITION *
0x18000f687  mov     rcx, r14; this
0x18000f68a  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000f68f  mov     rsi, rax
0x18000f692  test    rax, rax
0x18000f695  jnz     loc_18000F5B0
0x18000f69b  add     rsp, 20h
0x18000f69f  pop     r14
0x18000f6a1  pop     rdi
0x18000f6a2  pop     rsi
0x18000f6a3  pop     rbp
0x18000f6a4  pop     rbx
0x18000f6a5  retn
```
