# CWbemObject::ReadPropertyValue(long,long,long *,uchar *)

- ea: `0x180050cd0`
- end: `0x1800510ab`
- name: `?ReadPropertyValue@CWbemObject@@UEAAJJJPEAJPEAE@Z`
- size: `987`
- prototype: `int(CWbemObject *__hidden this, int, int, int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180013ae0`
- `0x180023bd0`
- `0x180024390`
- `0x180037120`
- `0x180038e50`
- `0x180050cd0`
- `0x1800510c0`
- `0x180051110`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180050e4a`
- `wbemcomn!GetMemLogObject` at `0x180050ec1`
- `wbemcomn!GetMemLogObject` at `0x180050efb`
- `wbemcomn!GetMemLogObject` at `0x180050f5a`
- `wbemcomn!GetMemLogObject` at `0x180050fb2`
- `wbemcomn!GetMemLogObject` at `0x180051019`
- `wbemcomn!GetMemLogObject` at `0x180051062`
- `wbemcomn!GetMemLogObject` at `0x180050e4a`
- `wbemcomn!GetMemLogObject` at `0x180050ec1`
- `wbemcomn!GetMemLogObject` at `0x180050efb`
- `wbemcomn!GetMemLogObject` at `0x180050f5a`
- `wbemcomn!GetMemLogObject` at `0x180050fb2`
- `wbemcomn!GetMemLogObject` at `0x180051019`
- `wbemcomn!GetMemLogObject` at `0x180051062`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050e58`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050ecf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050f09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050f68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050fc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180051027`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180051070`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050e58`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050ecf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050f09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050f68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180050fc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180051027`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180051070`

## pseudocode

```c
__int64 __fastcall CWbemObject::ReadPropertyValue(CWbemObject *this, int a2, int a3, int *a4, unsigned __int8 *a5)
{
  __int64 v6; // rcx
  unsigned int v9; // ebx
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // esi
  CCompressedString *v14; // rbx
  int v15; // eax
  int StringLength; // eax
  __int64 v17; // rdi
  int v18; // eax
  char *v19; // rdx
  unsigned __int8 *v20; // rcx
  int v21; // ecx
  __int64 v22; // r9
  __int64 result; // rax
  int i; // r8d
  __int16 v25; // ax
  CMemoryLog *v26; // rax
  CWbemRefreshingSvc *v27; // rcx
  CClassPart *v28; // rax
  CMemoryLog *v29; // rax
  __int64 v30; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v32; // rax
  CWbemRefreshingSvc *v33; // rcx
  __int64 v34; // rdx
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax

  v6 = *((_QWORD *)this + 16);
  v9 = (a2 >> 16) & 0x3FF;
  if ( (signed int)v9 > *(_DWORD *)(v6 + 20) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v30 = 84;
    goto LABEL_29;
  }
  if ( (unsigned int)CBitBlockTable<2>::GetBit(*(_QWORD *)v6, v9, 0) )
  {
    *a4 = 0;
    return 1;
  }
  if ( (unsigned int)CBitBlockTable<2>::GetBit(**((_QWORD **)this + 16), v9, 1) )
  {
    v28 = (CClassPart *)(*(__int64 (__fastcall **)(CWbemObject *))(*(_QWORD *)this + 800LL))(this);
    return CClassPart::GetDefaultByHandle(v28, a2, a3, a4, a5);
  }
  v11 = a2 & 0x1FFF;
  if ( a2 >= 0 )
  {
    v21 = ((unsigned int)a2 >> 26) & 0xF;
    *a4 = v21;
    if ( v21 > a3 )
    {
      v36 = GetMemLogObject();
      CMemoryLog::Write(v36, -2147217348);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749948LL;
      }
      v34 = 89;
      goto LABEL_34;
    }
    v22 = *((_QWORD *)this + 16);
    if ( (unsigned int)(v21 + v11) <= *(_DWORD *)(v22 + 16) )
    {
      memcpy_0(a5, (const void *)(*(_QWORD *)(v22 + 8) + (a2 & 0x1FFF)), (unsigned int)v21);
      return 0;
    }
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, -2147217400);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v30 = 90;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v27 + 2), v30, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v12 = *((_QWORD *)this + 16);
  if ( v11 + 4 > (unsigned __int64)*(unsigned int *)(v12 + 16) )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, -2147217400);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v30 = 85;
    goto LABEL_29;
  }
  v13 = *(_DWORD *)((a2 & 0x1FFF) + *(_QWORD *)(v12 + 8));
  v14 = CFastHeap::ResolveString(*((CFastHeap **)this + 17), v13);
  if ( !v14 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, -2147217400);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v30 = 86;
    goto LABEL_29;
  }
  v15 = CFastHeap::ElementMaxSize(*((CFastHeap **)this + 17), v13);
  if ( !CCompressedString::NValidateSize(v14, v15) )
  {
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2147217400);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v30 = 87;
    goto LABEL_29;
  }
  StringLength = CCompressedString::GetStringLength(v14);
  v17 = StringLength;
  v18 = 2 * StringLength;
  *a4 = v18 + 2;
  if ( v18 + 2 > a3 )
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, -2147217348);
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749948LL;
    }
    v34 = 88;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749948LL);
    return 2147749948LL;
  }
  v19 = (char *)v14 + 1;
  v20 = a5;
  if ( *(_BYTE *)v14 == 1 )
  {
    memcpy_0(a5, v19, v18);
  }
  else
  {
    for ( i = v17; i; --i )
    {
      v25 = *v19++;
      *(_WORD *)v20 = v25;
      v20 += 2;
    }
  }
  result = 0;
  *(_WORD *)&a5[2 * v17] = 0;
  return result;
}

```

## disassembly

```asm
0x180050cd0  push    rbx
0x180050cd2  push    rbp
0x180050cd3  push    rsi
0x180050cd4  push    rdi
0x180050cd5  push    r14
0x180050cd7  sub     rsp, 30h
0x180050cdb  mov     rdi, rcx
0x180050cde  mov     ebx, edx
0x180050ce0  mov     rcx, [rcx+80h]
0x180050ce7  mov     r14, r9
0x180050cea  sar     ebx, 10h
0x180050ced  mov     ebp, r8d
0x180050cf0  and     ebx, 3FFh
0x180050cf6  mov     esi, edx
0x180050cf8  cmp     ebx, [rcx+14h]
0x180050cfb  jg      loc_180050EFB
0x180050d01  mov     rcx, [rcx]
0x180050d04  xor     r8d, r8d
0x180050d07  mov     edx, ebx
0x180050d09  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x180050d0e  test    eax, eax
0x180050d10  jnz     loc_180050EB0
0x180050d16  mov     rcx, [rdi+80h]
0x180050d1d  lea     r8d, [rax+1]
0x180050d21  mov     edx, ebx
0x180050d23  mov     rcx, [rcx]
0x180050d26  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x180050d2b  test    eax, eax
0x180050d2d  jnz     loc_180050E7C
0x180050d33  mov     eax, esi
0x180050d35  mov     r10d, 1FFFh
0x180050d3b  and     eax, r10d
0x180050d3e  test    esi, esi
0x180050d40  jns     loc_180050DDC
0x180050d46  mov     rdx, [rdi+80h]
0x180050d4d  mov     r8d, eax
0x180050d50  add     rax, 4
0x180050d54  mov     ecx, [rdx+10h]
0x180050d57  cmp     rax, rcx
0x180050d5a  ja      loc_180050FB2
0x180050d60  mov     rax, [rdx+8]
0x180050d64  mov     rcx, [rdi+88h]; this
0x180050d6b  mov     esi, [r8+rax]
0x180050d6f  mov     edx, esi; unsigned int
0x180050d71  call    ?ResolveString@CFastHeap@@QEAAPEAVCCompressedString@@K@Z; CFastHeap::ResolveString(ulong)
0x180050d76  mov     rbx, rax
0x180050d79  test    rax, rax
0x180050d7c  jz      loc_180050E4A
0x180050d82  mov     rcx, [rdi+88h]; this
0x180050d89  mov     edx, esi; unsigned int
0x180050d8b  call    ?ElementMaxSize@CFastHeap@@QEAAHK@Z; CFastHeap::ElementMaxSize(ulong)
0x180050d90  mov     edx, eax; int
0x180050d92  mov     rcx, rbx; this
0x180050d95  call    ?NValidateSize@CCompressedString@@QEBA_NH@Z; CCompressedString::NValidateSize(int)
0x180050d9a  test    al, al
0x180050d9c  jz      loc_180050EC1
0x180050da2  mov     rcx, rbx; this
0x180050da5  call    ?GetStringLength@CCompressedString@@QEBAHXZ; CCompressedString::GetStringLength(void)
0x180050daa  movsxd  rdi, eax
0x180050dad  lea     eax, [rdi+rdi]
0x180050db0  lea     ecx, [rax+2]
0x180050db3  mov     [r14], ecx
0x180050db6  cmp     ecx, ebp
0x180050db8  jg      loc_180050F5A
0x180050dbe  cmp     byte ptr [rbx], 1
0x180050dc1  lea     rdx, [rbx+1]; Src
0x180050dc5  mov     rbx, [rsp+58h+arg_20]
0x180050dcd  mov     rcx, rbx; void *
0x180050dd0  jnz     short loc_180050E28
0x180050dd2  movsxd  r8, eax; Size
0x180050dd5  call    memcpy_0
0x180050dda  jmp     short loc_180050E42
0x180050ddc  mov     ecx, esi
0x180050dde  shr     ecx, 1Ah
0x180050de1  and     ecx, 0Fh
0x180050de4  mov     [r14], ecx
0x180050de7  cmp     ecx, ebp
0x180050de9  jg      loc_180051019
0x180050def  mov     r9, [rdi+80h]
0x180050df6  add     eax, ecx
0x180050df8  cmp     eax, [r9+10h]
0x180050dfc  ja      loc_180051062
0x180050e02  mov     r8d, ecx; Size
0x180050e05  mov     edx, esi
0x180050e07  mov     rcx, [rsp+58h+arg_20]; void *
0x180050e0f  and     rdx, r10
0x180050e12  add     rdx, [r9+8]; Src
0x180050e16  call    memcpy_0
0x180050e1b  xor     eax, eax
0x180050e1d  add     rsp, 30h
0x180050e21  pop     r14
0x180050e23  pop     rdi
0x180050e24  pop     rsi
0x180050e25  pop     rbp
0x180050e26  pop     rbx
0x180050e27  retn
0x180050e28  mov     r8d, edi
0x180050e2b  test    edi, edi
0x180050e2d  jz      short loc_180050E42
0x180050e2f  movsx   eax, byte ptr [rdx]
0x180050e32  inc     rdx
0x180050e35  mov     [rcx], ax
0x180050e38  lea     rcx, [rcx+2]
0x180050e3c  sub     r8d, 1
0x180050e40  jnz     short loc_180050E2F
0x180050e42  xor     eax, eax
0x180050e44  mov     [rbx+rdi*2], ax
0x180050e48  jmp     short loc_180050E1D
0x180050e4a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180050e50  mov     rcx, rax
0x180050e53  mov     edx, 80041008h
0x180050e58  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180050e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050e65  lea     rax, WPP_GLOBAL_Control
0x180050e6c  cmp     rcx, rax
0x180050e6f  jnz     loc_180050FFB
0x180050e75  mov     eax, 80041008h
0x180050e7a  jmp     short loc_180050E1D
0x180050e7c  mov     rax, [rdi]
0x180050e7f  mov     rcx, rdi
0x180050e82  mov     rax, [rax+320h]
0x180050e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e8e  mov     rcx, [rsp+58h+arg_20]
0x180050e96  mov     r9, r14; int *
0x180050e99  mov     [rsp+58h+var_38], rcx; unsigned __int8 *
0x180050e9e  mov     r8d, ebp; int
0x180050ea1  mov     rcx, rax; this
0x180050ea4  mov     edx, esi; int
0x180050ea6  call    ?GetDefaultByHandle@CClassPart@@QEAAJJJPEAJPEAE@Z; CClassPart::GetDefaultByHandle(long,long,long *,uchar *)
0x180050eab  jmp     loc_180050E1D
0x180050eb0  mov     dword ptr [r14], 0
0x180050eb7  mov     eax, 1
0x180050ebc  jmp     loc_180050E1D
0x180050ec1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180050ec7  mov     rcx, rax
0x180050eca  mov     edx, 80041008h
0x180050ecf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180050ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180050edc  lea     rax, WPP_GLOBAL_Control
0x180050ee3  cmp     rcx, rax
0x180050ee6  jz      short loc_180050E75
0x180050ee8  test    byte ptr [rcx+1Ch], 1
0x180050eec  jz      short loc_180050E75
0x180050eee  cmp     byte ptr [rcx+19h], 2
0x180050ef2  jb      short loc_180050E75
0x180050ef4  mov     edx, 57h ; 'W'
0x180050ef9  jmp     short loc_180050F3F
0x180050efb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180050f01  mov     rcx, rax
0x180050f04  mov     edx, 80041008h
0x180050f09  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180050f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050f16  lea     rax, WPP_GLOBAL_Control
0x180050f1d  cmp     rcx, rax
0x180050f20  jz      loc_180050E75
0x180050f26  test    byte ptr [rcx+1Ch], 1
0x180050f2a  jz      loc_180050E75
0x180050f30  cmp     byte ptr [rcx+19h], 2
0x180050f34  jb      loc_180050E75
0x180050f3a  mov     edx, 54h ; 'T'
0x180050f3f  mov     rcx, [rcx+10h]
0x180050f43  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180050f4a  mov     r9d, 80041008h
0x180050f50  call    WPP_SF_d
0x180050f55  jmp     loc_180050E75
0x180050f5a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180050f60  mov     rcx, rax
0x180050f63  mov     edx, 8004103Ch
0x180050f68  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180050f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050f75  lea     rax, WPP_GLOBAL_Control
0x180050f7c  cmp     rcx, rax
0x180050f7f  jz      short loc_180050FA8
0x180050f81  test    byte ptr [rcx+1Ch], 1
0x180050f85  jz      short loc_180050FA8
0x180050f87  cmp     byte ptr [rcx+19h], 2
0x180050f8b  jb      short loc_180050FA8
0x180050f8d  mov     edx, 58h ; 'X'
0x180050f92  mov     rcx, [rcx+10h]
0x180050f96  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180050f9d  mov     r9d, 8004103Ch
0x180050fa3  call    WPP_SF_d
0x180050fa8  mov     eax, 8004103Ch
0x180050fad  jmp     loc_180050E1D
0x180050fb2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180050fb8  mov     rcx, rax
0x180050fbb  mov     edx, 80041008h
0x180050fc0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180050fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180050fcd  lea     rax, WPP_GLOBAL_Control
0x180050fd4  cmp     rcx, rax
0x180050fd7  jz      loc_180050E75
0x180050fdd  test    byte ptr [rcx+1Ch], 1
0x180050fe1  jz      loc_180050E75
0x180050fe7  cmp     byte ptr [rcx+19h], 2
0x180050feb  jb      loc_180050E75
0x180050ff1  mov     edx, 55h ; 'U'
0x180050ff6  jmp     loc_180050F3F
0x180050ffb  test    byte ptr [rcx+1Ch], 1
0x180050fff  jz      loc_180050E75
0x180051005  cmp     byte ptr [rcx+19h], 2
0x180051009  jb      loc_180050E75
0x18005100f  mov     edx, 56h ; 'V'
0x180051014  jmp     loc_180050F3F
0x180051019  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005101f  mov     rcx, rax
0x180051022  mov     edx, 8004103Ch
0x180051027  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005102d  mov     rcx, cs:WPP_GLOBAL_Control
0x180051034  lea     rax, WPP_GLOBAL_Control
0x18005103b  cmp     rcx, rax
0x18005103e  jz      loc_180050FA8
0x180051044  test    byte ptr [rcx+1Ch], 1
0x180051048  jz      loc_180050FA8
0x18005104e  cmp     byte ptr [rcx+19h], 2
0x180051052  jb      loc_180050FA8
0x180051058  mov     edx, 59h ; 'Y'
0x18005105d  jmp     loc_180050F92
0x180051062  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180051068  mov     rcx, rax
0x18005106b  mov     edx, 80041008h
0x180051070  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180051076  mov     rcx, cs:WPP_GLOBAL_Control
0x18005107d  lea     rax, WPP_GLOBAL_Control
0x180051084  cmp     rcx, rax
0x180051087  jz      loc_180050E75
0x18005108d  test    byte ptr [rcx+1Ch], 1
0x180051091  jz      loc_180050E75
0x180051097  cmp     byte ptr [rcx+19h], 2
0x18005109b  jb      loc_180050E75
0x1800510a1  mov     edx, 5Ah ; 'Z'
0x1800510a6  jmp     loc_180050F3F
```
