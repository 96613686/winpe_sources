# CIPropertyStorageWrapper::WriteMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ulong)

- ea: `0x180011d00`
- end: `0x180011e8c`
- name: `?WriteMultiple@CIPropertyStorageWrapper@@UEAAJKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@K@Z`
- size: `396`
- prototype: `__int64 __fastcall(CIPropertyStorageWrapper *this, unsigned int, const struct tagPROPSPEC *const, const struct tagPROPVARIANT *const, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000115c`
- `0x1800110a8`
- `0x180011a00`
- `0x180011d00`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180011e6c`
- `KERNEL32!ReleaseMutex` at `0x180011e6c`
- `KERNEL32!WaitForSingleObject` at `0x180011d5c`
- `KERNEL32!WaitForSingleObject` at `0x180011d5c`
- `KERNEL32!lstrcmpiW` at `0x180011d99`
- `KERNEL32!lstrcmpiW` at `0x180011d99`

## pseudocode

```c
__int64 __fastcall CIPropertyStorageWrapper::WriteMultiple(
        CIPropertyStorageWrapper *this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        const struct tagPROPVARIANT *const a4,
        unsigned int a5)
{
  void *v9; // rcx
  unsigned int v11; // ebx
  CIPropertyStorageWrapper *v12; // rcx
  __int64 v13; // r15
  struct _propertyNodeDef *NewPropNodeWithName; // rbx
  const WCHAR *lpwstr; // r14
  int propid; // eax
  int v17; // esi
  struct _propertyNodeDef *v18; // rax

  if ( !a3 || !a4 || a5 - 2 > 0x7FFFFFFD )
    return 2147944180LL;
  v9 = (void *)*((_QWORD *)this + 5);
  if ( !v9 )
    return 2147680264LL;
  v11 = 0;
  WaitForSingleObject(v9, 0xFFFFFFFF);
  v13 = 0;
  *((_DWORD *)this + 8) = a5;
  if ( !a2 )
    goto LABEL_30;
  while ( 1 )
  {
    if ( !a3[(unsigned int)v13].ulKind )
    {
      NewPropNodeWithName = (struct _propertyNodeDef *)*((_QWORD *)this + 2);
      lpwstr = a3[(unsigned int)v13].lpwstr;
      if ( !NewPropNodeWithName )
        goto LABEL_34;
      do
      {
        if ( !*((_DWORD *)NewPropNodeWithName + 4) && !lstrcmpiW(*((LPCWSTR *)NewPropNodeWithName + 3), lpwstr) )
          break;
        NewPropNodeWithName = *(struct _propertyNodeDef **)NewPropNodeWithName;
      }
      while ( NewPropNodeWithName );
      if ( !NewPropNodeWithName )
      {
LABEL_34:
        NewPropNodeWithName = CIPropertyStorageWrapper::CreateNewPropNodeWithName(this, a3[(unsigned int)v13].lpwstr);
        if ( !NewPropNodeWithName )
        {
LABEL_14:
          v11 = -2147287032;
          goto LABEL_30;
        }
      }
LABEL_26:
      v11 = CIPropertyStorageWrapper::SetPropNodeData(v12, NewPropNodeWithName, &a4[v13]);
      goto LABEL_27;
    }
    propid = (int)a3[(unsigned int)v13].propid;
    if ( propid != -1 )
      break;
LABEL_27:
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= a2 )
      goto LABEL_30;
  }
  for ( NewPropNodeWithName = (struct _propertyNodeDef *)*((_QWORD *)this + 2);
        NewPropNodeWithName;
        NewPropNodeWithName = *(struct _propertyNodeDef **)NewPropNodeWithName )
  {
    if ( *((_DWORD *)NewPropNodeWithName + 5) == propid )
      goto LABEL_26;
  }
  v17 = (int)a3[(unsigned int)v13].propid;
  if ( (unsigned int)(propid - 2) <= 0x7FFFFFFD )
  {
    v18 = (struct _propertyNodeDef *)operator new(0x30u);
    NewPropNodeWithName = v18;
    if ( !v18 )
      goto LABEL_14;
    *(_OWORD *)v18 = 0;
    *((_OWORD *)v18 + 1) = 0;
    *((_OWORD *)v18 + 2) = 0;
    *((_DWORD *)v18 + 4) = 1;
    *((_DWORD *)v18 + 5) = v17;
    if ( *((_QWORD *)this + 2) )
    {
      *((_QWORD *)v18 + 1) = *((_QWORD *)this + 3);
      **((_QWORD **)this + 3) = v18;
    }
    else
    {
      *((_QWORD *)this + 2) = v18;
    }
    *((_QWORD *)this + 3) = v18;
    goto LABEL_26;
  }
  v11 = -2147286953;
LABEL_30:
  ReleaseMutex(*((HANDLE *)this + 5));
  return v11;
}

```

## disassembly

```asm
0x180011d00  push    rbx
0x180011d02  push    rbp
0x180011d03  push    rsi
0x180011d04  push    rdi
0x180011d05  push    r12
0x180011d07  push    r13
0x180011d09  push    r14
0x180011d0b  push    r15
0x180011d0d  sub     rsp, 28h
0x180011d11  mov     r12, r9
0x180011d14  mov     rbp, r8
0x180011d17  mov     r13d, edx
0x180011d1a  mov     rdi, rcx
0x180011d1d  test    r8, r8
0x180011d20  jz      loc_180011E76
0x180011d26  test    r9, r9
0x180011d29  jz      loc_180011E76
0x180011d2f  mov     esi, [rsp+68h+arg_20]
0x180011d36  lea     eax, [rsi-2]
0x180011d39  cmp     eax, 7FFFFFFDh
0x180011d3e  ja      loc_180011E76
0x180011d44  mov     rcx, [rcx+28h]; hHandle
0x180011d48  test    rcx, rcx
0x180011d4b  jnz     short loc_180011D57
0x180011d4d  mov     eax, 80030008h
0x180011d52  jmp     loc_180011E7B
0x180011d57  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011d5a  xor     ebx, ebx
0x180011d5c  call    cs:__imp_WaitForSingleObject
0x180011d62  xor     r15d, r15d
0x180011d65  mov     [rdi+20h], esi
0x180011d68  test    r13d, r13d
0x180011d6b  jz      loc_180011E68
0x180011d71  mov     esi, r15d
0x180011d74  add     rsi, rsi
0x180011d77  cmp     dword ptr [rbp+rsi*8+0], 0
0x180011d7c  jnz     short loc_180011DD3
0x180011d7e  mov     rbx, [rdi+10h]
0x180011d82  mov     r14, [rbp+rsi*8+8]
0x180011d87  test    rbx, rbx
0x180011d8a  jz      short loc_180011DB4
0x180011d8c  cmp     dword ptr [rbx+10h], 0
0x180011d90  jnz     short loc_180011DA3
0x180011d92  mov     rcx, [rbx+18h]; lpString1
0x180011d96  mov     rdx, r14; lpString2
0x180011d99  call    cs:__imp_lstrcmpiW
0x180011d9f  test    eax, eax
0x180011da1  jz      short loc_180011DAB
0x180011da3  mov     rbx, [rbx]
0x180011da6  test    rbx, rbx
0x180011da9  jnz     short loc_180011D8C
0x180011dab  test    rbx, rbx
0x180011dae  jnz     loc_180011E43
0x180011db4  mov     rdx, [rbp+rsi*8+8]; unsigned __int16 *
0x180011db9  mov     rcx, rdi; this
0x180011dbc  call    ?CreateNewPropNodeWithName@CIPropertyStorageWrapper@@QEAAPEAU_propertyNodeDef@@PEBG@Z; CIPropertyStorageWrapper::CreateNewPropNodeWithName(ushort const *)
0x180011dc1  mov     rbx, rax
0x180011dc4  test    rax, rax
0x180011dc7  jnz     short loc_180011E43
0x180011dc9  mov     ebx, 80030008h
0x180011dce  jmp     loc_180011E68
0x180011dd3  mov     eax, [rbp+rsi*8+8]
0x180011dd7  cmp     eax, 0FFFFFFFFh
0x180011dda  jz      short loc_180011E55
0x180011ddc  mov     rbx, [rdi+10h]
0x180011de0  jmp     short loc_180011DEA
0x180011de2  cmp     [rbx+14h], eax
0x180011de5  jz      short loc_180011E43
0x180011de7  mov     rbx, [rbx]
0x180011dea  test    rbx, rbx
0x180011ded  jnz     short loc_180011DE2
0x180011def  mov     esi, eax
0x180011df1  add     eax, 0FFFFFFFEh
0x180011df4  cmp     eax, 7FFFFFFDh
0x180011df9  ja      short loc_180011E63
0x180011dfb  lea     ecx, [rbx+30h]; Size
0x180011dfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011e03  mov     rbx, rax
0x180011e06  test    rax, rax
0x180011e09  jz      short loc_180011DC9
0x180011e0b  xorps   xmm0, xmm0
0x180011e0e  movups  xmmword ptr [rax], xmm0
0x180011e11  movups  xmmword ptr [rax+10h], xmm0
0x180011e15  movups  xmmword ptr [rax+20h], xmm0
0x180011e19  mov     dword ptr [rax+10h], 1
0x180011e20  mov     [rax+14h], esi
0x180011e23  cmp     qword ptr [rdi+10h], 0
0x180011e28  jnz     short loc_180011E30
0x180011e2a  mov     [rdi+10h], rax
0x180011e2e  jmp     short loc_180011E3F
0x180011e30  mov     rax, [rdi+18h]
0x180011e34  mov     [rbx+8], rax
0x180011e38  mov     rax, [rdi+18h]
0x180011e3c  mov     [rax], rbx
0x180011e3f  mov     [rdi+18h], rbx
0x180011e43  lea     rax, [r15+r15*2]
0x180011e47  mov     rdx, rbx; struct _propertyNodeDef *
0x180011e4a  lea     r8, [r12+rax*8]; struct tagPROPVARIANT *
0x180011e4e  call    ?SetPropNodeData@CIPropertyStorageWrapper@@QEAAJPEAU_propertyNodeDef@@PEBUtagPROPVARIANT@@@Z; CIPropertyStorageWrapper::SetPropNodeData(_propertyNodeDef *,tagPROPVARIANT const *)
0x180011e53  mov     ebx, eax
0x180011e55  inc     r15d
0x180011e58  cmp     r15d, r13d
0x180011e5b  jb      loc_180011D71
0x180011e61  jmp     short loc_180011E68
0x180011e63  mov     ebx, 80030057h
0x180011e68  mov     rcx, [rdi+28h]; hMutex
0x180011e6c  call    cs:__imp_ReleaseMutex
0x180011e72  mov     eax, ebx
0x180011e74  jmp     short loc_180011E7B
0x180011e76  mov     eax, 800706F4h
0x180011e7b  add     rsp, 28h
0x180011e7f  pop     r15
0x180011e81  pop     r14
0x180011e83  pop     r13
0x180011e85  pop     r12
0x180011e87  pop     rdi
0x180011e88  pop     rsi
0x180011e89  pop     rbp
0x180011e8a  pop     rbx
0x180011e8b  retn
```
