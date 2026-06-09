# JoltProperties::CopyPropertiesFrom(DBInfoProps const *,ulong,ulong,_GUID)

- ea: `0x1001f370`
- end: `0x1001f4e3`
- name: `?CopyPropertiesFrom@JoltProperties@@UAEJPBUDBInfoProps@@KKU_GUID@@@Z`
- size: `371`
- prototype: `int __thiscall(JoltProperties *__hidden this, const struct DBInfoProps *, unsigned int, unsigned int, struct _GUID)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1001c6d0`
- `0x1001f370`
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
        struct _GUID a5)
{
  void (__thiscall ***v6)(_DWORD, int); // eax
  _DWORD *v7; // esi
  unsigned int v8; // eax
  bool v9; // cf
  size_t v10; // eax
  _DWORD *v11; // eax
  _DWORD *v12; // eax
  unsigned int v14; // edx
  _DWORD *v16; // [esp+14h] [ebp-14h]
  _DWORD *v17; // [esp+18h] [ebp-10h]
  unsigned int v18; // [esp+18h] [ebp-10h]

  v6 = (void (__thiscall ***)(_DWORD, int))*((_DWORD *)this + 4);
  v7 = (_DWORD *)((char *)this + 16);
  if ( v6 )
  {
    if ( *(v6 - 1) )
    {
      (**v6)(v6, 3);
      v7 = (_DWORD *)((char *)this + 16);
    }
    else
    {
      operator delete(v6 - 1);
    }
    *v7 = 0;
    *((_DWORD *)this + 2) = 0;
    *((_DWORD *)this + 3) = 0;
    v17 = (_DWORD *)((char *)this + 16);
  }
  else
  {
    v17 = (_DWORD *)((char *)this + 16);
  }
  *((_DWORD *)this + 3) = a4;
  *((_DWORD *)this + 2) = a4;
  v8 = 48 * a4;
  if ( !is_mul_ok(0x30u, a4) )
    v8 = -1;
  v9 = __CFADD__(v8, 4);
  v10 = v8 + 4;
  if ( v9 )
    v10 = -1;
  v11 = operator new(v10);
  if ( v11 )
  {
    *v11 = a4;
    v16 = v11 + 1;
    `eh vector constructor iterator'(
      v11 + 1,
      0x30u,
      a4,
      (void (__thiscall *)(void *))JoltProperty::JoltProperty,
      (void (__thiscall *)(void *))JoltColumnProperty::~JoltColumnProperty);
    v12 = v16;
  }
  else
  {
    v12 = 0;
  }
  *v17 = v12;
  if ( v12 )
  {
    v14 = 0;
    v18 = 0;
    for ( *(struct _GUID *)((char *)this + 20) = a5; v14 < *((_DWORD *)this + 2); v7 = (_DWORD *)((char *)this + 16) )
    {
      (*(void (__thiscall **)(unsigned int, char *))(*(_DWORD *)(*v7 + 48 * v14) + 12))(
        *v7 + 48 * v14,
        (char *)a2 + 28 * a3 + 28 * v14);
      v14 = v18 + 1;
      v18 = v14;
    }
    return 0;
  }
  else
  {
    *v7 = 0;
    *((_DWORD *)this + 2) = 0;
    *((_DWORD *)this + 3) = 0;
    return -2147024882;
  }
}

```

## disassembly

```asm
0x1001f370  mov     edi, edi
0x1001f372  push    ebp
0x1001f373  mov     ebp, esp
0x1001f375  push    0FFFFFFFFh
0x1001f377  push    offset ?CopyPropertiesFrom@JoltEnforceDBNULLIDProperties@@UAEJPBUDBInfoProps@@KKU_GUID@@@Z_SEH
0x1001f37c  mov     eax, large fs:0
0x1001f382  push    eax
0x1001f383  sub     esp, 10h
0x1001f386  push    esi
0x1001f387  push    edi
0x1001f388  mov     eax, ___security_cookie
0x1001f38d  xor     eax, ebp
0x1001f38f  push    eax
0x1001f390  lea     eax, [ebp+var_C]
0x1001f393  mov     large fs:0, eax
0x1001f399  mov     edi, ecx
0x1001f39b  mov     [ebp+var_18], edi
0x1001f39e  mov     eax, [edi+10h]
0x1001f3a1  lea     esi, [edi+10h]
0x1001f3a4  mov     [ebp+var_10], eax
0x1001f3a7  test    eax, eax
0x1001f3a9  jz      short loc_1001F3F1
0x1001f3ab  cmp     dword ptr [eax-4], 0
0x1001f3af  lea     ecx, [eax-4]
0x1001f3b2  jz      short loc_1001F3CC
0x1001f3b4  mov     eax, [eax]
0x1001f3b6  push    3
0x1001f3b8  mov     esi, [eax]
0x1001f3ba  mov     ecx, esi
0x1001f3bc  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f3c2  mov     ecx, [ebp+var_10]
0x1001f3c5  call    esi
0x1001f3c7  lea     esi, [edi+10h]
0x1001f3ca  jmp     short loc_1001F3D5
0x1001f3cc  push    ecx; Block
0x1001f3cd  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001f3d2  add     esp, 4
0x1001f3d5  lea     eax, [edi+10h]
0x1001f3d8  mov     dword ptr [esi], 0
0x1001f3de  mov     dword ptr [edi+8], 0
0x1001f3e5  mov     dword ptr [edi+0Ch], 0
0x1001f3ec  mov     [ebp+var_10], eax
0x1001f3ef  jmp     short loc_1001F3F4
0x1001f3f1  mov     [ebp+var_10], esi
0x1001f3f4  mov     eax, [ebp+arg_8]
0x1001f3f7  mov     ecx, 30h ; '0'
0x1001f3fc  mov     [edi+0Ch], eax
0x1001f3ff  mov     [edi+8], eax
0x1001f402  mul     ecx
0x1001f404  mov     ecx, 0FFFFFFFFh
0x1001f409  cmovb   eax, ecx
0x1001f40c  add     eax, 4
0x1001f40f  cmovb   eax, ecx
0x1001f412  push    eax; Size
0x1001f413  call    ??2@YAPAXI@Z; operator new(uint)
0x1001f418  add     esp, 4
0x1001f41b  mov     [ebp+Block], eax
0x1001f41e  mov     [ebp+var_4], 0
0x1001f425  test    eax, eax
0x1001f427  jz      short loc_1001F44C
0x1001f429  mov     ecx, [ebp+arg_8]
0x1001f42c  push    offset ??1JoltColumnProperty@@UAE@XZ; void (__thiscall *)(void *)
0x1001f431  push    offset ??0JoltProperty@@QAE@XZ; void (__thiscall *)(void *)
0x1001f436  push    ecx; unsigned int
0x1001f437  mov     [eax], ecx
0x1001f439  add     eax, 4
0x1001f43c  push    30h ; '0'; unsigned int
0x1001f43e  push    eax; void *
0x1001f43f  mov     [ebp+var_14], eax
0x1001f442  call    ??_L@YGXPAXIIP6EX0@Z1@Z; `eh vector constructor iterator'(void *,uint,uint,void (*)(void *),void (*)(void *))
0x1001f447  mov     eax, [ebp+var_14]
0x1001f44a  jmp     short loc_1001F44E
0x1001f44c  xor     eax, eax
0x1001f44e  mov     ecx, [ebp+var_10]
0x1001f451  mov     [ebp+var_4], 0FFFFFFFFh
0x1001f458  mov     [ecx], eax
0x1001f45a  test    eax, eax
0x1001f45c  jnz     short loc_1001F47E
0x1001f45e  mov     [esi], eax
0x1001f460  mov     [edi+8], eax
0x1001f463  mov     [edi+0Ch], eax
0x1001f466  mov     eax, 8007000Eh
0x1001f46b  mov     ecx, [ebp+var_C]
0x1001f46e  mov     large fs:0, ecx
0x1001f475  pop     ecx
0x1001f476  pop     edi
0x1001f477  pop     esi
0x1001f478  mov     esp, ebp
0x1001f47a  pop     ebp
0x1001f47b  retn    1Ch
0x1001f47e  movups  xmm0, xmmword ptr [ebp+arg_C.Data1]
0x1001f482  xor     edx, edx
0x1001f484  mov     [ebp+var_10], edx
0x1001f487  movups  xmmword ptr [edi+14h], xmm0
0x1001f48b  cmp     [edi+8], edx
0x1001f48e  jbe     short loc_1001F4CE
0x1001f490  mov     ecx, [ebp+arg_0]
0x1001f493  lea     edi, [edx+edx*2]
0x1001f496  add     edx, [ebp+arg_4]
0x1001f499  shl     edi, 4
0x1001f49c  add     edi, [esi]
0x1001f49e  lea     eax, ds:0[edx*8]
0x1001f4a5  sub     eax, edx
0x1001f4a7  mov     esi, [edi]
0x1001f4a9  lea     eax, [ecx+eax*4]
0x1001f4ac  mov     esi, [esi+0Ch]
0x1001f4af  mov     ecx, esi
0x1001f4b1  push    eax
0x1001f4b2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f4b8  mov     ecx, edi
0x1001f4ba  call    esi
0x1001f4bc  mov     eax, [ebp+var_18]
0x1001f4bf  mov     edx, [ebp+var_10]
0x1001f4c2  inc     edx
0x1001f4c3  mov     [ebp+var_10], edx
0x1001f4c6  lea     esi, [eax+10h]
0x1001f4c9  cmp     edx, [eax+8]
0x1001f4cc  jb      short loc_1001F490
0x1001f4ce  xor     eax, eax
0x1001f4d0  mov     ecx, [ebp+var_C]
0x1001f4d3  mov     large fs:0, ecx
0x1001f4da  pop     ecx
0x1001f4db  pop     edi
0x1001f4dc  pop     esi
0x1001f4dd  mov     esp, ebp
0x1001f4df  pop     ebp
0x1001f4e0  retn    1Ch
0x1004e710  mov     eax, [ebp+Block]
0x1004e713  push    eax; Block
0x1004e714  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004e719  pop     ecx
0x1004e71a  retn
0x1004e720  nop
0x1004e721  nop
0x1004e722  mov     edx, [esp-4+arg_4]
0x1004e726  lea     eax, [edx+0Ch]
0x1004e729  mov     ecx, [edx-1Ch]
0x1004e72c  xor     ecx, eax; StackCookie
0x1004e72e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e733  mov     eax, offset stru_1004FAB4
0x1004e738  jmp     ___CxxFrameHandler3
```
