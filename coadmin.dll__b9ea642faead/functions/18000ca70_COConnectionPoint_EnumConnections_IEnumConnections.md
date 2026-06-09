# COConnectionPoint::EnumConnections(IEnumConnections * *)

- ea: `0x18000ca70`
- end: `0x18000cbee`
- name: `?EnumConnections@COConnectionPoint@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, struct IEnumConnections **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001064`
- `0x1800010a4`
- `0x1800010b0`
- `0x1800010bc`
- `0x18000c5e8`
- `0x18000ca70`
- `0x18000cdd8`
- `0x180010010`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cbd2`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cbd2`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000caa8`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000caa8`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::EnumConnections(COConnectionPoint *this, struct IEnumConnections **a2)
{
  int v4; // ebx
  struct tagCONNECTDATA *v5; // rbp
  __int64 v6; // rdx
  unsigned int i; // r8d
  DWORD v8; // r9d
  __int64 v9; // rax
  COEnumConnections *v10; // rax
  COEnumConnections *v11; // rsi

  if ( a2 )
  {
    *a2 = 0;
    if ( *((_DWORD *)this + 10) )
    {
      return (unsigned int)-2147418113;
    }
    else
    {
      CReaderWriterLock3::ReadLock((COConnectionPoint *)((char *)this + 8));
      if ( *((_DWORD *)this + 10) )
      {
        v4 = -2147418113;
      }
      else
      {
        v4 = -2147221500;
        if ( *((_DWORD *)this + 6) )
        {
          v5 = (struct tagCONNECTDATA *)operator new[](saturated_mul(*((unsigned int *)this + 6), 0x10u));
          if ( v5 )
          {
            v6 = 0;
            for ( i = 0; (unsigned int)v6 < *((_DWORD *)this + 7); v6 = (unsigned int)(v6 + 1) )
            {
              if ( i >= *((_DWORD *)this + 6) )
                break;
              v8 = *(_DWORD *)(*((_QWORD *)this + 4) + 8 * v6);
              if ( v8 )
              {
                v9 = i++;
                v5[v9].dwCookie = v8;
                v5[v9].pUnk = 0;
              }
            }
            v10 = (COEnumConnections *)operator new(0x28u);
            v11 = v10;
            if ( v10 )
            {
              *((_DWORD *)v10 + 2) = 0;
              *(_QWORD *)v10 = &COEnumConnections::`vftable';
              *((_QWORD *)v10 + 2) = this;
              *((_QWORD *)v10 + 3) = 0;
              *((_QWORD *)v10 + 4) = 0;
              v4 = COEnumConnections::Init(
                     v10,
                     *((_DWORD *)this + 6),
                     v5,
                     0,
                     *((struct IGlobalInterfaceTable **)this + 6));
              if ( v4 < 0
                || (v4 = (**(__int64 (__fastcall ***)(COEnumConnections *, GUID *, struct IEnumConnections **))v11)(
                           v11,
                           &IID_IEnumConnections,
                           a2),
                    v4 < 0) )
              {
                COEnumConnections::~COEnumConnections(v11);
                operator delete(v11);
              }
            }
            else
            {
              v4 = -2147024882;
            }
            operator delete[](v5);
          }
          else
          {
            v4 = -2147024882;
          }
        }
      }
      CReaderWriterLock3::ReadUnlock((COConnectionPoint *)((char *)this + 8));
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ca70  push    rbx
0x18000ca72  push    rbp
0x18000ca73  push    rsi
0x18000ca74  push    rdi
0x18000ca75  push    r14
0x18000ca77  push    r15
0x18000ca79  sub     rsp, 38h
0x18000ca7d  mov     r14, rdx
0x18000ca80  mov     rdi, rcx
0x18000ca83  test    rdx, rdx
0x18000ca86  jz      loc_18000CBDA
0x18000ca8c  mov     qword ptr [rdx], 0
0x18000ca93  mov     eax, [rcx+28h]
0x18000ca96  test    eax, eax
0x18000ca98  jz      short loc_18000CAA4
0x18000ca9a  mov     ebx, 8000FFFFh
0x18000ca9f  jmp     loc_18000CBDF
0x18000caa4  add     rcx, 8
0x18000caa8  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000caae  mov     eax, [rdi+28h]
0x18000cab1  test    eax, eax
0x18000cab3  jz      short loc_18000CABF
0x18000cab5  mov     ebx, 8000FFFFh
0x18000caba  jmp     loc_18000CBCE
0x18000cabf  cmp     dword ptr [rdi+18h], 0
0x18000cac3  mov     ebx, 80040004h
0x18000cac8  jz      loc_18000CBCE
0x18000cace  mov     ecx, [rdi+18h]
0x18000cad1  mov     eax, 10h
0x18000cad6  mul     rcx
0x18000cad9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cae0  cmovb   rax, rcx
0x18000cae4  mov     rcx, rax; unsigned __int64
0x18000cae7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000caec  mov     rbp, rax
0x18000caef  test    rax, rax
0x18000caf2  jz      loc_18000CBC9
0x18000caf8  xor     edx, edx
0x18000cafa  xor     r8d, r8d
0x18000cafd  cmp     [rdi+1Ch], edx
0x18000cb00  jbe     short loc_18000CB33
0x18000cb02  cmp     r8d, [rdi+18h]
0x18000cb06  jnb     short loc_18000CB33
0x18000cb08  mov     rax, [rdi+20h]
0x18000cb0c  mov     r9d, [rax+rdx*8]
0x18000cb10  test    r9d, r9d
0x18000cb13  jz      short loc_18000CB2C
0x18000cb15  mov     eax, r8d
0x18000cb18  add     rax, rax
0x18000cb1b  inc     r8d
0x18000cb1e  mov     [rbp+rax*8+8], r9d
0x18000cb23  mov     qword ptr [rbp+rax*8+0], 0
0x18000cb2c  inc     edx
0x18000cb2e  cmp     edx, [rdi+1Ch]
0x18000cb31  jb      short loc_18000CB02
0x18000cb33  mov     ecx, 28h ; '('; Size
0x18000cb38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cb3d  mov     rsi, rax
0x18000cb40  test    rax, rax
0x18000cb43  jz      short loc_18000CBBA
0x18000cb45  mov     dword ptr [rsi+8], 0
0x18000cb4c  lea     rax, ??_7COEnumConnections@@6B@; const COEnumConnections::`vftable'
0x18000cb53  mov     [rsi], rax
0x18000cb56  xor     r9d, r9d; unsigned int
0x18000cb59  mov     [rsi+10h], rdi
0x18000cb5d  mov     r8, rbp; struct tagCONNECTDATA *
0x18000cb60  mov     qword ptr [rsi+18h], 0
0x18000cb68  mov     rcx, rsi; this
0x18000cb6b  mov     qword ptr [rsi+20h], 0
0x18000cb73  mov     rax, [rdi+30h]
0x18000cb77  mov     edx, [rdi+18h]; unsigned int
0x18000cb7a  mov     [rsp+68h+var_48], rax; struct IGlobalInterfaceTable *
0x18000cb7f  call    ?Init@COEnumConnections@@QEAAJKPEAUtagCONNECTDATA@@KPEAUIGlobalInterfaceTable@@@Z; COEnumConnections::Init(ulong,tagCONNECTDATA *,ulong,IGlobalInterfaceTable *)
0x18000cb84  mov     ebx, eax
0x18000cb86  test    eax, eax
0x18000cb88  js      short loc_18000CBA8
0x18000cb8a  mov     rax, [rsi]
0x18000cb8d  lea     rdx, IID_IEnumConnections
0x18000cb94  mov     r8, r14
0x18000cb97  mov     rcx, rsi
0x18000cb9a  mov     rax, [rax]
0x18000cb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cba2  mov     ebx, eax
0x18000cba4  test    eax, eax
0x18000cba6  jns     short loc_18000CBBF
0x18000cba8  mov     rcx, rsi; this
0x18000cbab  call    ??1COEnumConnections@@QEAA@XZ; COEnumConnections::~COEnumConnections(void)
0x18000cbb0  mov     rcx, rsi; Block
0x18000cbb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cbb8  jmp     short loc_18000CBBF
0x18000cbba  mov     ebx, 8007000Eh
0x18000cbbf  mov     rcx, rbp; Block
0x18000cbc2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000cbc7  jmp     short loc_18000CBCE
0x18000cbc9  mov     ebx, 8007000Eh
0x18000cbce  lea     rcx, [rdi+8]
0x18000cbd2  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000cbd8  jmp     short loc_18000CBDF
0x18000cbda  mov     ebx, 80070057h
0x18000cbdf  mov     eax, ebx
0x18000cbe1  add     rsp, 38h
0x18000cbe5  pop     r15
0x18000cbe7  pop     r14
0x18000cbe9  pop     rdi
0x18000cbea  pop     rsi
0x18000cbeb  pop     rbp
0x18000cbec  pop     rbx
0x18000cbed  retn
```
