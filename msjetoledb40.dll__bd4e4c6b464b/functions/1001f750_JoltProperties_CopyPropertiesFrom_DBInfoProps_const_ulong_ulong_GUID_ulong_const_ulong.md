# JoltProperties::CopyPropertiesFrom(DBInfoProps const *,ulong,ulong,_GUID,ulong const *,ulong)

- ea: `0x1001f750`
- end: `0x1001f8d0`
- name: `?CopyPropertiesFrom@JoltProperties@@UAEJPBUDBInfoProps@@KKU_GUID@@PBKK@Z`
- size: `384`
- prototype: `int __thiscall(JoltProperties *__hidden this, const struct DBInfoProps *, unsigned int, unsigned int, struct _GUID, const unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1001c6d0`
- `0x1001f750`
- `0x1004b3f0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`
- `0x1004d8cb`

## pseudocode

```c
int __thiscall JoltProperties::CopyPropertiesFrom(
        JoltProperties *this,
        const struct DBInfoProps *a2,
        unsigned int a3,
        unsigned int a4,
        struct _GUID a5,
        const unsigned int *a6,
        unsigned int a7)
{
  JoltProperties *v7; // edi
  void (__thiscall ***v8)(_DWORD, int); // eax
  char *v9; // ecx
  unsigned int v10; // eax
  bool v11; // cf
  size_t v12; // eax
  _DWORD *v13; // eax
  _DWORD *v14; // esi
  int result; // eax
  unsigned int v16; // esi
  const struct DBInfoProps *Prop; // eax
  unsigned int v18; // [esp+0h] [ebp-24h]
  _DWORD *v20; // [esp+14h] [ebp-10h]
  unsigned int v21; // [esp+14h] [ebp-10h]

  v7 = this;
  v8 = (void (__thiscall ***)(_DWORD, int))*((_DWORD *)this + 4);
  v9 = (char *)this + 16;
  if ( v8 )
  {
    if ( *(v8 - 1) )
      (**v8)(v8, 3);
    else
      operator delete(v8 - 1);
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 2) = 0;
    *((_DWORD *)v7 + 3) = 0;
    v20 = (_DWORD *)((char *)v7 + 16);
  }
  else
  {
    v20 = v9;
  }
  *((_DWORD *)v7 + 3) = a7;
  v10 = 48 * a7;
  *((_DWORD *)v7 + 2) = a7;
  if ( !is_mul_ok(0x30u, a7) )
    v10 = -1;
  v11 = __CFADD__(v10, 4);
  v12 = v10 + 4;
  if ( v11 )
    v12 = -1;
  v13 = operator new(v12);
  if ( v13 )
  {
    *v13 = a7;
    v14 = v13 + 1;
    `eh vector constructor iterator'(
      v13 + 1,
      0x30u,
      a7,
      (void (__thiscall *)(void *))JoltProperty::JoltProperty,
      (void (__thiscall *)(void *))JoltColumnProperty::~JoltColumnProperty);
  }
  else
  {
    v14 = 0;
  }
  *v20 = v14;
  if ( !v14 )
    return -2147024882;
  v16 = 0;
  v21 = 0;
  *(struct _GUID *)((char *)v7 + 20) = a5;
  if ( !*((_DWORD *)v7 + 2) )
    return 0;
  do
  {
    Prop = FindProp(*(struct _GUID *)((char *)v7 + 20), v18);
    result = (*(int (__thiscall **)(unsigned int, const struct DBInfoProps *))(*(_DWORD *)(48 * v16 + *((_DWORD *)v7 + 4))
                                                                             + 12))(
               48 * v16 + *((_DWORD *)v7 + 4),
               Prop);
    if ( result < 0 )
      break;
    v7 = this;
    v16 = v21 + 1;
    v21 = v16;
  }
  while ( v16 < *((_DWORD *)this + 2) );
  return result;
}

```

## disassembly

```asm
0x1001f750  mov     edi, edi
0x1001f752  push    ebp
0x1001f753  mov     ebp, esp
0x1001f755  push    0FFFFFFFFh
0x1001f757  push    offset ?CopyPropertiesFrom@JoltProperties@@UAEJPBUDBInfoProps@@KKU_GUID@@PBKK@Z_SEH
0x1001f75c  mov     eax, large fs:0
0x1001f762  push    eax
0x1001f763  sub     esp, 0Ch
0x1001f766  push    esi
0x1001f767  push    edi
0x1001f768  mov     eax, ___security_cookie
0x1001f76d  xor     eax, ebp
0x1001f76f  push    eax; unsigned int
0x1001f770  lea     eax, [ebp+var_C]
0x1001f773  mov     large fs:0, eax
0x1001f779  mov     edi, ecx
0x1001f77b  mov     [ebp+var_14], edi
0x1001f77e  mov     eax, [edi+10h]
0x1001f781  lea     ecx, [edi+10h]
0x1001f784  mov     [ebp+var_10], eax
0x1001f787  test    eax, eax
0x1001f789  jz      short loc_1001F7CF
0x1001f78b  cmp     dword ptr [eax-4], 0
0x1001f78f  lea     ecx, [eax-4]
0x1001f792  jz      short loc_1001F7A9
0x1001f794  mov     eax, [eax]
0x1001f796  push    3
0x1001f798  mov     esi, [eax]
0x1001f79a  mov     ecx, esi
0x1001f79c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f7a2  mov     ecx, [ebp+var_10]
0x1001f7a5  call    esi
0x1001f7a7  jmp     short loc_1001F7B2
0x1001f7a9  push    ecx; Block
0x1001f7aa  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001f7af  add     esp, 4
0x1001f7b2  lea     eax, [edi+10h]
0x1001f7b5  mov     dword ptr [edi+10h], 0
0x1001f7bc  mov     dword ptr [edi+8], 0
0x1001f7c3  mov     dword ptr [edi+0Ch], 0
0x1001f7ca  mov     [ebp+var_10], eax
0x1001f7cd  jmp     short loc_1001F7D2
0x1001f7cf  mov     [ebp+var_10], ecx
0x1001f7d2  mov     esi, [ebp+arg_20]
0x1001f7d5  mov     ecx, 30h ; '0'
0x1001f7da  mov     eax, esi
0x1001f7dc  mov     [edi+0Ch], esi
0x1001f7df  mul     ecx
0x1001f7e1  mov     ecx, 0FFFFFFFFh
0x1001f7e6  mov     [edi+8], esi
0x1001f7e9  cmovb   eax, ecx
0x1001f7ec  add     eax, 4
0x1001f7ef  cmovb   eax, ecx
0x1001f7f2  push    eax; Size
0x1001f7f3  call    ??2@YAPAXI@Z; operator new(uint)
0x1001f7f8  add     esp, 4
0x1001f7fb  mov     [ebp+Block], eax
0x1001f7fe  mov     [ebp+var_4], 0
0x1001f805  test    eax, eax
0x1001f807  jz      short loc_1001F825
0x1001f809  push    offset ??1JoltColumnProperty@@UAE@XZ; void (__thiscall *)(void *)
0x1001f80e  push    offset ??0JoltProperty@@QAE@XZ; void (__thiscall *)(void *)
0x1001f813  push    [ebp+arg_20]; unsigned int
0x1001f816  mov     [eax], esi
0x1001f818  lea     esi, [eax+4]
0x1001f81b  push    30h ; '0'; unsigned int
0x1001f81d  push    esi; void *
0x1001f81e  call    ??_L@YGXPAXIIP6EX0@Z1@Z; `eh vector constructor iterator'(void *,uint,uint,void (*)(void *),void (*)(void *))
0x1001f823  jmp     short loc_1001F827
0x1001f825  xor     esi, esi
0x1001f827  mov     eax, [ebp+var_10]
0x1001f82a  mov     [ebp+var_4], 0FFFFFFFFh
0x1001f831  mov     [eax], esi
0x1001f833  test    esi, esi
0x1001f835  jnz     short loc_1001F84F
0x1001f837  mov     eax, 8007000Eh
0x1001f83c  mov     ecx, [ebp+var_C]
0x1001f83f  mov     large fs:0, ecx
0x1001f846  pop     ecx
0x1001f847  pop     edi
0x1001f848  pop     esi
0x1001f849  mov     esp, ebp
0x1001f84b  pop     ebp
0x1001f84c  retn    24h ; '$'
0x1001f84f  movups  xmm0, xmmword ptr [ebp+arg_C.Data1]
0x1001f853  xor     esi, esi
0x1001f855  mov     [ebp+var_10], esi
0x1001f858  movups  xmmword ptr [edi+14h], xmm0
0x1001f85c  cmp     [edi+8], esi
0x1001f85f  jbe     short loc_1001F8BB
0x1001f861  movups  xmm0, xmmword ptr [edi+14h]
0x1001f865  sub     esp, 10h
0x1001f868  mov     eax, esp
0x1001f86a  movups  xmmword ptr [eax], xmm0
0x1001f86d  mov     eax, [ebp+arg_1C]
0x1001f870  mov     ecx, [eax+esi*4]
0x1001f873  call    ?FindProp@@YGPBUDBInfoProps@@U_GUID@@K@Z; FindProp(_GUID,ulong)
0x1001f878  mov     edi, [edi+10h]
0x1001f87b  lea     ecx, [esi+esi*2]
0x1001f87e  shl     ecx, 4
0x1001f881  add     edi, ecx
0x1001f883  push    eax
0x1001f884  mov     eax, [edi]
0x1001f886  mov     esi, [eax+0Ch]
0x1001f889  mov     ecx, esi
0x1001f88b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f891  mov     ecx, edi
0x1001f893  call    esi
0x1001f895  test    eax, eax
0x1001f897  js      short loc_1001F8BD
0x1001f899  mov     esi, [ebp+var_10]
0x1001f89c  mov     edi, [ebp+var_14]
0x1001f89f  inc     esi
0x1001f8a0  mov     [ebp+var_10], esi
0x1001f8a3  cmp     esi, [edi+8]
0x1001f8a6  jb      short loc_1001F861
0x1001f8a8  mov     ecx, [ebp+var_C]
0x1001f8ab  mov     large fs:0, ecx
0x1001f8b2  pop     ecx
0x1001f8b3  pop     edi
0x1001f8b4  pop     esi
0x1001f8b5  mov     esp, ebp
0x1001f8b7  pop     ebp
0x1001f8b8  retn    24h ; '$'
0x1001f8bb  xor     eax, eax
0x1001f8bd  mov     ecx, [ebp+var_C]
0x1001f8c0  mov     large fs:0, ecx
0x1001f8c7  pop     ecx
0x1001f8c8  pop     edi
0x1001f8c9  pop     esi
0x1001f8ca  mov     esp, ebp
0x1001f8cc  pop     ebp
0x1001f8cd  retn    24h ; '$'
0x1004e750  mov     eax, [ebp+Block]
0x1004e753  push    eax; Block
0x1004e754  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004e759  pop     ecx
0x1004e75a  retn
0x1004e760  nop
0x1004e761  nop
0x1004e762  mov     edx, [esp-4+arg_4]
0x1004e766  lea     eax, [edx+0Ch]
0x1004e769  mov     ecx, [edx-18h]
0x1004e76c  xor     ecx, eax; StackCookie
0x1004e76e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e773  mov     eax, offset stru_1004FAE0
0x1004e778  jmp     ___CxxFrameHandler3
```
