# WSTExportSecurityContext(unsigned __int64,ulong,_SecBuffer *,void * *)

- ea: `0x180018f28`
- end: `0x180019079`
- name: `?WSTExportSecurityContext@@YAJ_KKPEAU_SecBuffer@@PEAPEAX@Z`
- size: `337`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, struct _SecBuffer *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019560`

## callees

- `0x18000c700`
- `0x18000ea3c`
- `0x180015a58`
- `0x180018ea0`
- `0x180018f28`
- `0x18001ece2`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall WSTExportSecurityContext(unsigned __int64 a1, unsigned int a2, struct _SecBuffer *a3, void **a4)
{
  int v9; // eax
  struct _NEGOEXTS_UMODE_CONTEXT *v10; // rdi
  int v11; // ebx
  unsigned int v12; // esi
  int v13; // ebp
  char *v14; // rax
  void *v15; // rbx
  struct _NEGOEXTS_UMODE_CONTEXT *v16; // [rsp+30h] [rbp-58h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-50h] BYREF

  v16 = 0;
  *(_OWORD *)Src = 0;
  if ( (a2 & 1) != 0 )
    return 2148074242LL;
  if ( a4 )
    *a4 = 0;
  a3->pvBuffer = 0;
  *(_QWORD *)&a3->cbBuffer = 0;
  v9 = WSTReferenceUserModeContextByLsaHandle(a1, 0, &v16);
  v10 = v16;
  v11 = v9;
  if ( v9 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void **, void **))(*((_QWORD *)v16 + 6) + 96LL))(
            *((_QWORD *)v16 + 4),
            a2,
            Src,
            a4);
    if ( v11 >= 0 )
    {
      v12 = ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 24;
      if ( ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) >= 0xFFFFFFE8 )
      {
        v11 = -1073741675;
      }
      else
      {
        v13 = *((_DWORD *)v10 + 10);
        v14 = (char *)NegoExtsAllocate(v12);
        v15 = v14;
        if ( v14 )
        {
          *(_QWORD *)v14 = 0;
          *((_DWORD *)v14 + 2) = v13;
          *((_DWORD *)v14 + 3) = 20;
          *((_DWORD *)v14 + 4) = Src[0];
          memcpy_0(v14 + 20, Src[1], LODWORD(Src[0]));
          a3->pvBuffer = v15;
          v11 = 0;
          a3->cbBuffer = v12;
        }
        else
        {
          v11 = -1073741801;
        }
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids, a1, v9);
  }
  if ( v10 )
    WSTDereferenceUserModeContext(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180018f28  push    rbx
0x180018f2a  push    rbp
0x180018f2b  push    rsi
0x180018f2c  push    rdi
0x180018f2d  push    r14
0x180018f2f  push    r15
0x180018f31  sub     rsp, 58h
0x180018f35  mov     [rsp+88h+var_58], 0
0x180018f3e  xorps   xmm0, xmm0
0x180018f41  mov     rsi, r9
0x180018f44  mov     r14, r8
0x180018f47  mov     r15d, edx
0x180018f4a  mov     rbp, rcx
0x180018f4d  movups  xmmword ptr [rsp+88h+Src], xmm0
0x180018f52  test    dl, 1
0x180018f55  jz      short loc_180018F61
0x180018f57  mov     eax, 80090302h
0x180018f5c  jmp     loc_18001906C
0x180018f61  test    rsi, rsi
0x180018f64  jz      short loc_180018F6D
0x180018f66  mov     qword ptr [r9], 0
0x180018f6d  mov     qword ptr [r8+8], 0
0x180018f75  xor     edx, edx; unsigned __int8
0x180018f77  mov     qword ptr [r8], 0
0x180018f7e  lea     r8, [rsp+88h+var_58]; struct _NEGOEXTS_UMODE_CONTEXT **
0x180018f83  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_NEGOEXTS_UMODE_CONTEXT * *)
0x180018f88  mov     rdi, [rsp+88h+var_58]
0x180018f8d  mov     ebx, eax
0x180018f8f  test    eax, eax
0x180018f91  jns     short loc_180018FD5
0x180018f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f9a  lea     rax, WPP_GLOBAL_Control
0x180018fa1  cmp     rcx, rax
0x180018fa4  jz      loc_18001905D
0x180018faa  test    byte ptr [rcx+1Ch], 1
0x180018fae  jz      loc_18001905D
0x180018fb4  mov     rcx, [rcx+10h]
0x180018fb8  lea     r8, WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids
0x180018fbf  mov     edx, 0Eh
0x180018fc4  mov     [rsp+88h+var_68], ebx
0x180018fc8  mov     r9, rbp
0x180018fcb  call    WPP_SF_qD
0x180018fd0  jmp     loc_18001905D
0x180018fd5  mov     rax, [rdi+30h]
0x180018fd9  lea     r8, [rsp+88h+Src]
0x180018fde  mov     rcx, [rdi+20h]
0x180018fe2  mov     r9, rsi
0x180018fe5  mov     edx, r15d
0x180018fe8  mov     rax, [rax+60h]
0x180018fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ff1  mov     ebx, eax
0x180018ff3  test    eax, eax
0x180018ff5  js      short loc_18001905D
0x180018ff7  mov     esi, dword ptr [rsp+88h+Src]
0x180018ffb  add     esi, 7
0x180018ffe  and     esi, 0FFFFFFF8h
0x180019001  add     esi, 18h
0x180019004  cmp     esi, 18h
0x180019007  jb      short loc_180019058
0x180019009  mov     ebp, [rdi+28h]
0x18001900c  mov     ecx, esi; unsigned __int64
0x18001900e  call    ?NegoExtsAllocate@@YAPEAX_K@Z; NegoExtsAllocate(unsigned __int64)
0x180019013  mov     rbx, rax
0x180019016  test    rax, rax
0x180019019  jnz     short loc_180019022
0x18001901b  mov     ebx, 0C0000017h
0x180019020  jmp     short loc_18001905D
0x180019022  mov     qword ptr [rax], 0
0x180019029  lea     rcx, [rax+14h]; void *
0x18001902d  mov     [rax+8], ebp
0x180019030  mov     eax, ecx
0x180019032  sub     eax, ebx
0x180019034  mov     [rbx+0Ch], eax
0x180019037  mov     eax, dword ptr [rsp+88h+Src]
0x18001903b  mov     [rbx+10h], eax
0x18001903e  mov     r8d, dword ptr [rsp+88h+Src]; Size
0x180019043  mov     rdx, [rsp+88h+Src+8]; Src
0x180019048  call    memcpy_0
0x18001904d  mov     [r14+8], rbx
0x180019051  xor     ebx, ebx
0x180019053  mov     [r14], esi
0x180019056  jmp     short loc_18001905D
0x180019058  mov     ebx, 0C0000095h
0x18001905d  test    rdi, rdi
0x180019060  jz      short loc_18001906A
0x180019062  mov     rcx, rdi; struct _NEGOEXTS_UMODE_CONTEXT *
0x180019065  call    ?WSTDereferenceUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x18001906a  mov     eax, ebx
0x18001906c  add     rsp, 58h
0x180019070  pop     r15
0x180019072  pop     r14
0x180019074  pop     rdi
0x180019075  pop     rsi
0x180019076  pop     rbp
0x180019077  pop     rbx
0x180019078  retn
```
