# CClfsKernelMarshallingContext::Flush(void)

- ea: `0x14005584c`
- end: `0x140055a39`
- name: `?Flush@CClfsKernelMarshallingContext@@QEAAJXZ`
- size: `493`
- prototype: `__int64 __fastcall(CClfsKernelMarshallingContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140058210`

## callees

- `0x140005840`
- `0x14000bf48`
- `0x140055440`
- `0x14005584c`
- `0x1400577c0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055885`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055885`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400559fe`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400559fe`
- `ntoskrnl!KeBugCheckEx` at `0x1400559be`
- `ntoskrnl!KeBugCheckEx` at `0x1400559be`

## pseudocode

```c
__int64 __fastcall CClfsKernelMarshallingContext::Flush(CClfsKernelMarshallingContext *this)
{
  int v2; // esi
  BOOLEAN v3; // r12
  _QWORD **v4; // r15
  union _CLS_LSN *v5; // rdi
  char v6; // al
  _QWORD *v7; // r14
  union _CLS_LSN v8; // rax
  _QWORD *v9; // rdx
  ULONG_PTR v10; // r8
  _QWORD *v11; // r10
  _QWORD *v12; // r11
  char v13; // cl
  _QWORD *v14; // rax
  unsigned int v16; // [rsp+88h] [rbp+10h] BYREF
  union _CLS_LSN v17; // [rsp+90h] [rbp+18h] BYREF
  union _CLS_LSN v18; // [rsp+98h] [rbp+20h] BYREF

  v2 = 0;
  v16 = 0;
  v17.ullOffset = 0;
  if ( !*((_DWORD *)this + 16) )
    return 0;
  v3 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 18), 1u);
  v4 = (_QWORD **)((char *)this + 152);
  if ( *v4 != v4 )
  {
    v17 = *(union _CLS_LSN *)((char *)this + 104);
    v2 = ClfsFlushToLsnInternal(*(CLFS_LSN *)((char *)this + 8), 0, &v17, &v16);
    if ( v2 >= 0 )
    {
      v5 = (union _CLS_LSN *)((char *)this + 112);
      if ( this == (CClfsKernelMarshallingContext *)-112LL )
      {
        v6 = 0;
      }
      else
      {
        if ( *((_QWORD *)this + 14) >= v17.ullOffset )
        {
LABEL_9:
          v7 = *v4;
          v8 = CLFS_LSN_INVALID;
          while ( 1 )
          {
            if ( v7 == v4 )
              goto LABEL_29;
            v9 = v7 - 17;
            v10 = *((_QWORD *)this + 16);
            if ( (_QWORD *)v10 == v7 - 17 )
              KeBugCheckEx(0xC1F5u, 0x41u, v10, (ULONG_PTR)(v7 - 17), (ULONG_PTR)this);
            v11 = v7;
            v12 = (_QWORD *)*v7;
            v7 = (_QWORD *)*v7;
            if ( v9[1] == -24 || this == (CClfsKernelMarshallingContext *)-112LL )
              break;
            if ( *(_QWORD *)(v9[1] + 24LL) < *((_QWORD *)this + 14) )
            {
              v13 = 1;
              goto LABEL_16;
            }
LABEL_23:
            if ( this != (CClfsKernelMarshallingContext *)-112LL && v8.ullOffset == v5->ullOffset )
            {
LABEL_17:
              if ( (_QWORD *)v12[1] != v11 || (v14 = (_QWORD *)v11[1], (_QWORD *)*v14 != v11) )
                __fastfail(3u);
              *v14 = v12;
              v12[1] = v14;
              CClfsKernelMarshallingContext::DeallocateIocb(this, v9);
              _InterlockedDecrement((volatile signed __int32 *)this + 10);
              v8 = CLFS_LSN_INVALID;
            }
          }
          v13 = 0;
LABEL_16:
          if ( v13 )
            goto LABEL_17;
          goto LABEL_23;
        }
        v6 = 1;
      }
      if ( v6 )
        *v5 = v17;
      goto LABEL_9;
    }
  }
  v8 = CLFS_LSN_INVALID;
LABEL_29:
  if ( v2 == -1072037848 || v2 == -1072037845 )
  {
    v18 = v8;
    CClfsKernelMarshallingContext::ReleaseFlushElements(this, &v18);
  }
  if ( v3 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 18), (ERESOURCE_THREAD)KeGetCurrentThread());
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14005584c  mov     rax, rsp
0x14005584f  mov     [rax+8], rcx
0x140055853  push    rbx
0x140055854  push    rsi
0x140055855  push    rdi
0x140055856  push    r12
0x140055858  push    r14
0x14005585a  push    r15
0x14005585c  sub     rsp, 48h
0x140055860  mov     rbx, rcx
0x140055863  xor     esi, esi
0x140055865  mov     [rax-44h], esi
0x140055868  mov     [rax-48h], sil
0x14005586c  mov     [rax+10h], esi
0x14005586f  mov     [rax+18h], rsi
0x140055873  cmp     [rcx+40h], esi
0x140055876  jz      loc_140055A1B
0x14005587c  mov     dl, 1; Wait
0x14005587e  mov     rcx, [rcx+90h]; Resource
0x140055885  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005588c  nop     dword ptr [rax+rax+00h]
0x140055891  mov     r12b, al
0x140055894  mov     [rsp+78h+var_48], al
0x140055898  lea     r15, [rbx+98h]
0x14005589f  cmp     [r15], r15
0x1400558a2  jz      loc_1400559D2
0x1400558a8  mov     rax, [rbx+68h]
0x1400558ac  mov     [rsp+78h+arg_10], rax
0x1400558b4  lea     r9, [rsp+78h+arg_8]
0x1400558bc  lea     r8, [rsp+78h+arg_10]
0x1400558c4  xor     edx, edx
0x1400558c6  mov     rcx, [rbx+8]
0x1400558ca  call    ClfsFlushToLsnInternal
0x1400558cf  mov     esi, eax
0x1400558d1  mov     [rsp+78h+var_44], eax
0x1400558d5  test    eax, eax
0x1400558d7  js      loc_1400559D2
0x1400558dd  lea     rdi, [rbx+70h]
0x1400558e1  test    rdi, rdi
0x1400558e4  jz      loc_140055999
0x1400558ea  mov     ecx, [rdi+4]
0x1400558ed  cmp     ecx, dword ptr [rsp+78h+arg_10+4]
0x1400558f4  ja      short loc_140055914
0x1400558f6  jnz     short loc_140055903
0x1400558f8  mov     eax, dword ptr [rsp+78h+arg_10]
0x1400558ff  cmp     [rdi], eax
0x140055901  jnb     short loc_140055914
0x140055903  mov     al, 1
0x140055905  test    al, al
0x140055907  jz      short loc_140055914
0x140055909  mov     rax, [rsp+78h+arg_10]
0x140055911  mov     [rdi], rax
0x140055914  mov     r14, [r15]
0x140055917  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14005591e  cmp     r14, r15
0x140055921  jz      loc_1400559D9
0x140055927  lea     rdx, [r14-88h]; Entry
0x14005592e  mov     r8, [rbx+80h]; BugCheckParameter2
0x140055935  cmp     r8, rdx
0x140055938  jz      short loc_1400559AC
0x14005593a  mov     r10, r14
0x14005593d  mov     r11, [r14]
0x140055940  mov     r14, r11
0x140055943  mov     r8, [rdx+8]
0x140055947  add     r8, 18h
0x14005594b  jz      short loc_140055995
0x14005594d  test    rdi, rdi
0x140055950  jz      short loc_140055995
0x140055952  mov     ecx, [rdi+4]
0x140055955  cmp     [r8+4], ecx
0x140055959  ja      short loc_1400559A0
0x14005595b  jnz     short loc_140055964
0x14005595d  mov     ecx, [rdi]
0x14005595f  cmp     [r8], ecx
0x140055962  jnb     short loc_1400559A0
0x140055964  mov     cl, 1
0x140055966  test    cl, cl
0x140055968  jz      short loc_1400559A0
0x14005596a  cmp     [r11+8], r10
0x14005596e  jnz     short loc_1400559CB
0x140055970  mov     rax, [r10+8]
0x140055974  cmp     [rax], r10
0x140055977  jnz     short loc_1400559CB
0x140055979  mov     [rax], r11
0x14005597c  mov     [r11+8], rax
0x140055980  mov     rcx, rbx; this
0x140055983  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140055988  lock dec dword ptr [rbx+28h]
0x14005598c  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140055993  jmp     short loc_14005591E
0x140055995  xor     cl, cl
0x140055997  jmp     short loc_140055966
0x140055999  xor     al, al
0x14005599b  jmp     loc_140055905
0x1400559a0  test    rdi, rdi
0x1400559a3  jz      short loc_140055993
0x1400559a5  cmp     rax, [rdi]
0x1400559a8  jnz     short loc_140055993
0x1400559aa  jmp     short loc_14005596A
0x1400559ac  mov     [rsp+78h+BugCheckParameter4], rbx; BugCheckParameter4
0x1400559b1  mov     r9, rdx; BugCheckParameter3
0x1400559b4  mov     edx, 41h ; 'A'; BugCheckParameter1
0x1400559b9  mov     ecx, 0C1F5h; BugCheckCode
0x1400559be  call    cs:__imp_KeBugCheckEx
0x1400559cb  mov     ecx, 3
0x1400559d0  int     29h; Win8: RtlFailFast(ecx)
0x1400559d2  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400559d9  cmp     esi, 0C01A0028h
0x1400559df  jz      short loc_140055A1F
0x1400559e1  cmp     esi, 0C01A002Bh
0x1400559e7  jz      short loc_140055A1F
0x1400559e9  test    r12b, r12b
0x1400559ec  jz      short loc_140055A0A
0x1400559ee  mov     rdx, gs:188h; ResourceThreadId
0x1400559f7  mov     rcx, [rbx+90h]; Resource
0x1400559fe  call    cs:__imp_ExReleaseResourceForThreadLite
0x140055a05  nop     dword ptr [rax+rax+00h]
0x140055a0a  mov     eax, esi
0x140055a0c  add     rsp, 48h
0x140055a10  pop     r15
0x140055a12  pop     r14
0x140055a14  pop     r12
0x140055a16  pop     rdi
0x140055a17  pop     rsi
0x140055a18  pop     rbx
0x140055a19  retn
0x140055a1b  xor     eax, eax
0x140055a1d  jmp     short loc_140055A0C
0x140055a1f  mov     qword ptr [rsp+78h+arg_18], rax
0x140055a27  lea     rdx, [rsp+78h+arg_18]; union _CLS_LSN *
0x140055a2f  mov     rcx, rbx; this
0x140055a32  call    ?ReleaseFlushElements@CClfsKernelMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsKernelMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x140055a37  jmp     short loc_1400559E9
0x1400797c3  push    rbp
0x1400797c5  sub     rsp, 30h
0x1400797c9  mov     rbp, rdx
0x1400797cc  cmp     dword ptr [rbp+34h], 0C01A0028h
0x1400797d3  jz      short loc_1400797DE
0x1400797d5  cmp     dword ptr [rbp+34h], 0C01A002Bh
0x1400797dc  jnz     short loc_140079800
0x1400797de  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400797e5  mov     [rbp+98h], rax
0x1400797ec  lea     rdx, [rbp+98h]; union _CLS_LSN *
0x1400797f3  mov     rcx, [rbp+80h]; this
0x1400797fa  call    ?ReleaseFlushElements@CClfsKernelMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsKernelMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x1400797ff  nop
0x140079800  cmp     byte ptr [rbp+30h], 0
0x140079804  jz      short loc_14007981D
0x140079806  mov     rcx, [rbp+80h]
0x14007980d  mov     rcx, [rcx+90h]
0x140079814  call    ClfsReleaseResourceLite
0x140079819  mov     byte ptr [rbp+30h], 0
0x14007981d  add     rsp, 30h
0x140079821  pop     rbp
0x140079822  retn
```
