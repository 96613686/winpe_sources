# JoltEnforceDBNULLIDProperties::CopyPropertiesFrom(DBInfoProps const *,ulong,ulong,_GUID)

- ea: `0x1001f5a0`
- end: `0x1001f713`
- name: `?CopyPropertiesFrom@JoltEnforceDBNULLIDProperties@@UAEJPBUDBInfoProps@@KKU_GUID@@@Z`
- size: `371`
- prototype: `int __thiscall(JoltEnforceDBNULLIDProperties *__hidden this, const struct DBInfoProps *, unsigned int, unsigned int, struct _GUID)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1001c6d0`
- `0x1001f5a0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`
- `0x1004d8cb`

## pseudocode

```c
int __thiscall JoltEnforceDBNULLIDProperties::CopyPropertiesFrom(
        JoltEnforceDBNULLIDProperties *this,
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
      (void (__thiscall *)(void *))JoltColumnProperty::JoltColumnProperty,
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
0x1001f5a0  mov     edi, edi
0x1001f5a2  push    ebp
0x1001f5a3  mov     ebp, esp
0x1001f5a5  push    0FFFFFFFFh
0x1001f5a7  push    offset ?CopyPropertiesFrom@JoltEnforceDBNULLIDProperties@@UAEJPBUDBInfoProps@@KKU_GUID@@@Z_SEH
0x1001f5ac  mov     eax, large fs:0
0x1001f5b2  push    eax
0x1001f5b3  sub     esp, 10h
0x1001f5b6  push    esi
0x1001f5b7  push    edi
0x1001f5b8  mov     eax, ___security_cookie
0x1001f5bd  xor     eax, ebp
0x1001f5bf  push    eax
0x1001f5c0  lea     eax, [ebp+var_C]
0x1001f5c3  mov     large fs:0, eax
0x1001f5c9  mov     edi, ecx
0x1001f5cb  mov     [ebp+var_18], edi
0x1001f5ce  mov     eax, [edi+10h]
0x1001f5d1  lea     esi, [edi+10h]
0x1001f5d4  mov     [ebp+var_10], eax
0x1001f5d7  test    eax, eax
0x1001f5d9  jz      short loc_1001F621
0x1001f5db  cmp     dword ptr [eax-4], 0
0x1001f5df  lea     ecx, [eax-4]
0x1001f5e2  jz      short loc_1001F5FC
0x1001f5e4  mov     eax, [eax]
0x1001f5e6  push    3
0x1001f5e8  mov     esi, [eax]
0x1001f5ea  mov     ecx, esi
0x1001f5ec  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f5f2  mov     ecx, [ebp+var_10]
0x1001f5f5  call    esi
0x1001f5f7  lea     esi, [edi+10h]
0x1001f5fa  jmp     short loc_1001F605
0x1001f5fc  push    ecx; Block
0x1001f5fd  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001f602  add     esp, 4
0x1001f605  lea     eax, [edi+10h]
0x1001f608  mov     dword ptr [esi], 0
0x1001f60e  mov     dword ptr [edi+8], 0
0x1001f615  mov     dword ptr [edi+0Ch], 0
0x1001f61c  mov     [ebp+var_10], eax
0x1001f61f  jmp     short loc_1001F624
0x1001f621  mov     [ebp+var_10], esi
0x1001f624  mov     eax, [ebp+arg_8]
0x1001f627  mov     ecx, 30h ; '0'
0x1001f62c  mov     [edi+0Ch], eax
0x1001f62f  mov     [edi+8], eax
0x1001f632  mul     ecx
0x1001f634  mov     ecx, 0FFFFFFFFh
0x1001f639  cmovb   eax, ecx
0x1001f63c  add     eax, 4
0x1001f63f  cmovb   eax, ecx
0x1001f642  push    eax; Size
0x1001f643  call    ??2@YAPAXI@Z; operator new(uint)
0x1001f648  add     esp, 4
0x1001f64b  mov     [ebp+var_1C], eax
0x1001f64e  mov     [ebp+var_4], 0
0x1001f655  test    eax, eax
0x1001f657  jz      short loc_1001F67C
0x1001f659  mov     ecx, [ebp+arg_8]
0x1001f65c  push    offset ??1JoltColumnProperty@@UAE@XZ; void (__thiscall *)(void *)
0x1001f661  push    offset ??0JoltColumnProperty@@QAE@XZ; void (__thiscall *)(void *)
0x1001f666  push    ecx; unsigned int
0x1001f667  mov     [eax], ecx
0x1001f669  add     eax, 4
0x1001f66c  push    30h ; '0'; unsigned int
0x1001f66e  push    eax; void *
0x1001f66f  mov     [ebp+var_14], eax
0x1001f672  call    ??_L@YGXPAXIIP6EX0@Z1@Z; `eh vector constructor iterator'(void *,uint,uint,void (*)(void *),void (*)(void *))
0x1001f677  mov     eax, [ebp+var_14]
0x1001f67a  jmp     short loc_1001F67E
0x1001f67c  xor     eax, eax
0x1001f67e  mov     ecx, [ebp+var_10]
0x1001f681  mov     [ebp+var_4], 0FFFFFFFFh
0x1001f688  mov     [ecx], eax
0x1001f68a  test    eax, eax
0x1001f68c  jnz     short loc_1001F6AE
0x1001f68e  mov     [esi], eax
0x1001f690  mov     [edi+8], eax
0x1001f693  mov     [edi+0Ch], eax
0x1001f696  mov     eax, 8007000Eh
0x1001f69b  mov     ecx, [ebp+var_C]
0x1001f69e  mov     large fs:0, ecx
0x1001f6a5  pop     ecx
0x1001f6a6  pop     edi
0x1001f6a7  pop     esi
0x1001f6a8  mov     esp, ebp
0x1001f6aa  pop     ebp
0x1001f6ab  retn    1Ch
0x1001f6ae  movups  xmm0, xmmword ptr [ebp+arg_C.Data1]
0x1001f6b2  xor     edx, edx
0x1001f6b4  mov     [ebp+var_10], edx
0x1001f6b7  movups  xmmword ptr [edi+14h], xmm0
0x1001f6bb  cmp     [edi+8], edx
0x1001f6be  jbe     short loc_1001F6FE
0x1001f6c0  mov     ecx, [ebp+arg_0]
0x1001f6c3  lea     edi, [edx+edx*2]
0x1001f6c6  add     edx, [ebp+arg_4]
0x1001f6c9  shl     edi, 4
0x1001f6cc  add     edi, [esi]
0x1001f6ce  lea     eax, ds:0[edx*8]
0x1001f6d5  sub     eax, edx
0x1001f6d7  mov     esi, [edi]
0x1001f6d9  lea     eax, [ecx+eax*4]
0x1001f6dc  mov     esi, [esi+0Ch]
0x1001f6df  mov     ecx, esi
0x1001f6e1  push    eax
0x1001f6e2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f6e8  mov     ecx, edi
0x1001f6ea  call    esi
0x1001f6ec  mov     eax, [ebp+var_18]
0x1001f6ef  mov     edx, [ebp+var_10]
0x1001f6f2  inc     edx
0x1001f6f3  mov     [ebp+var_10], edx
0x1001f6f6  lea     esi, [eax+10h]
0x1001f6f9  cmp     edx, [eax+8]
0x1001f6fc  jb      short loc_1001F6C0
0x1001f6fe  xor     eax, eax
0x1001f700  mov     ecx, [ebp+var_C]
0x1001f703  mov     large fs:0, ecx
0x1001f70a  pop     ecx
0x1001f70b  pop     edi
0x1001f70c  pop     esi
0x1001f70d  mov     esp, ebp
0x1001f70f  pop     ebp
0x1001f710  retn    1Ch
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
