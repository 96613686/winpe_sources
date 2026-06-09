# CAssociationCallback::OnInitOobAssociationComplete(ushort const *,ulong,_DEVPROPERTY * const,long)

- ea: `0x140017d90`
- end: `0x140017f4d`
- name: `?OnInitOobAssociationComplete@CAssociationCallback@@UEAAJPEBGKQEAU_DEVPROPERTY@@J@Z`
- size: `445`
- prototype: `__int64 __fastcall(CAssociationCallback *this, const unsigned __int16 *, unsigned int, struct _DEVPROPERTY *const, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140009060`
- `0x14000a8ac`
- `0x14000b7c4`
- `0x1400137f8`
- `0x140017d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017f34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017efb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017efb`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::OnInitOobAssociationComplete(
        CAssociationCallback *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _DEVPROPERTY *const a4,
        int a5)
{
  signed int v5; // ebx
  __int64 v10; // rbp
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdi
  _WORD *v14; // rax
  __int64 v15; // rcx
  unsigned __int16 *v16; // rax
  unsigned __int16 **v17; // rsi
  unsigned __int64 v18; // rdi
  int v19; // r9d
  const unsigned __int16 *v20; // rcx
  unsigned int inited; // ebx

  v5 = a5;
  v10 = 0;
  if ( a5 < 0 )
  {
    v13 = 0;
    goto LABEL_24;
  }
  if ( a2 )
  {
    v11 = 0x7FFFFFFF;
    v12 = a2;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v5 = v11 == 0 ? 0x80070057 : 0;
    if ( v11 )
    {
      v13 = (2 * (0x7FFFFFFF - v11)) & -(__int64)(v11 != 0);
      goto LABEL_10;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  v13 = 0;
LABEL_10:
  if ( v5 < 0 )
    goto LABEL_24;
  v14 = (_WORD *)*((_QWORD *)this + 5);
  if ( v14 )
  {
    v15 = 0x7FFFFFFF;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v15;
    }
    while ( v15 );
    v5 = v15 == 0 ? 0x80070057 : 0;
    if ( v15 )
      v10 = (2 * (0x7FFFFFFF - v15)) & -(__int64)(v15 != 0);
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v5 < 0 )
    goto LABEL_24;
  v16 = (unsigned __int16 *)DAF_user_alloc(v13 + 2);
  *((_QWORD *)this + 8) = v16;
  if ( !v16 )
  {
    v5 = -2147024882;
    goto LABEL_24;
  }
  v5 = StringCbCopyW(v16, v13 + 2, a2);
  if ( v5 < 0 )
  {
LABEL_24:
    v17 = (unsigned __int16 **)((char *)this + 72);
    if ( v5 < 0 )
      goto LABEL_28;
    goto LABEL_25;
  }
  v17 = (unsigned __int16 **)((char *)this + 72);
  *((_QWORD *)this + 9) = DAF_user_alloc(v13 + v10 + 4);
LABEL_25:
  v18 = v10 + v13 + 4;
  v5 = StringCbCopyW(*v17, v18, *((const unsigned __int16 **)this + 5));
  if ( v5 >= 0 )
  {
    v5 = StringCbCatW(*v17, v18, L"#");
    if ( v5 >= 0 )
      v5 = StringCbCatW(*v17, v18, a2);
  }
LABEL_28:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 26) )
  {
    if ( v5 < 0 )
      v20 = 0;
    else
      v20 = *v17;
    inited = OnInitOobAssociationCompleteStub(v20, a3, a4, v19, *((void **)this + 4));
  }
  else
  {
    inited = -2140930029;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return inited;
}

```

## disassembly

```asm
0x140017d90  push    rbx
0x140017d92  push    rbp
0x140017d93  push    rsi
0x140017d94  push    rdi
0x140017d95  push    r12
0x140017d97  push    r13
0x140017d99  push    r14
0x140017d9b  push    r15
0x140017d9d  sub     rsp, 38h
0x140017da1  mov     ebx, [rsp+78h+arg_20]
0x140017da8  xor     esi, esi
0x140017daa  mov     r12, r9
0x140017dad  mov     r13d, r8d
0x140017db0  mov     r15, rdx
0x140017db3  mov     r14, rcx
0x140017db6  mov     ebp, esi
0x140017db8  test    ebx, ebx
0x140017dba  js      loc_140017EA8
0x140017dc0  mov     r10d, 7FFFFFFFh
0x140017dc6  test    rdx, rdx
0x140017dc9  jz      short loc_140017E0C
0x140017dcb  mov     edx, r10d
0x140017dce  mov     rax, r15
0x140017dd1  cmp     [rax], si
0x140017dd4  jz      short loc_140017DE0
0x140017dd6  add     rax, 2
0x140017dda  sub     rdx, 1
0x140017dde  jnz     short loc_140017DD1
0x140017de0  mov     rax, rdx
0x140017de3  mov     r8d, 80070057h
0x140017de9  neg     rax
0x140017dec  sbb     ebx, ebx
0x140017dee  not     ebx
0x140017df0  and     ebx, r8d
0x140017df3  test    rdx, rdx
0x140017df6  jz      short loc_140017E15
0x140017df8  mov     rax, r10
0x140017dfb  sub     rax, rdx
0x140017dfe  add     rax, rax
0x140017e01  neg     rdx
0x140017e04  sbb     rdi, rdi
0x140017e07  and     rdi, rax
0x140017e0a  jmp     short loc_140017E18
0x140017e0c  mov     r8d, 80070057h
0x140017e12  mov     ebx, r8d
0x140017e15  mov     rdi, rsi
0x140017e18  test    ebx, ebx
0x140017e1a  js      loc_140017EAB
0x140017e20  mov     rax, [rcx+28h]
0x140017e24  test    rax, rax
0x140017e27  jz      short loc_140017E5E
0x140017e29  mov     rcx, r10
0x140017e2c  cmp     [rax], si
0x140017e2f  jz      short loc_140017E3B
0x140017e31  add     rax, 2
0x140017e35  sub     rcx, 1
0x140017e39  jnz     short loc_140017E2C
0x140017e3b  mov     rax, rcx
0x140017e3e  neg     rax
0x140017e41  sbb     ebx, ebx
0x140017e43  not     ebx
0x140017e45  and     ebx, r8d
0x140017e48  test    rcx, rcx
0x140017e4b  jz      short loc_140017E61
0x140017e4d  sub     r10, rcx
0x140017e50  add     r10, r10
0x140017e53  neg     rcx
0x140017e56  sbb     rbp, rbp
0x140017e59  and     rbp, r10
0x140017e5c  jmp     short loc_140017E61
0x140017e5e  mov     ebx, r8d
0x140017e61  test    ebx, ebx
0x140017e63  js      short loc_140017EAB
0x140017e65  lea     rcx, [rdi+2]
0x140017e69  call    DAF_user_alloc
0x140017e6e  mov     [r14+40h], rax
0x140017e72  test    rax, rax
0x140017e75  jnz     short loc_140017E7E
0x140017e77  mov     ebx, 8007000Eh
0x140017e7c  jmp     short loc_140017EAB
0x140017e7e  mov     r8, r15; unsigned __int16 *
0x140017e81  lea     rdx, [rdi+2]; unsigned __int64
0x140017e85  mov     rcx, rax; unsigned __int16 *
0x140017e88  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140017e8d  mov     ebx, eax
0x140017e8f  test    eax, eax
0x140017e91  js      short loc_140017EAB
0x140017e93  lea     rcx, [rbp+4]
0x140017e97  add     rcx, rdi
0x140017e9a  lea     rsi, [r14+48h]
0x140017e9e  call    DAF_user_alloc
0x140017ea3  mov     [rsi], rax
0x140017ea6  jmp     short loc_140017EB3
0x140017ea8  mov     rdi, rsi
0x140017eab  lea     rsi, [r14+48h]
0x140017eaf  test    ebx, ebx
0x140017eb1  js      short loc_140017EF7
0x140017eb3  mov     r8, [r14+28h]; unsigned __int16 *
0x140017eb7  add     rdi, 4
0x140017ebb  mov     rcx, [rsi]; unsigned __int16 *
0x140017ebe  add     rdi, rbp
0x140017ec1  mov     rdx, rdi; unsigned __int64
0x140017ec4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140017ec9  mov     ebx, eax
0x140017ecb  test    eax, eax
0x140017ecd  js      short loc_140017EF7
0x140017ecf  mov     rcx, [rsi]; unsigned __int16 *
0x140017ed2  lea     r8, asc_140024788; "#"
0x140017ed9  mov     rdx, rdi; unsigned __int64
0x140017edc  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140017ee1  mov     ebx, eax
0x140017ee3  test    eax, eax
0x140017ee5  js      short loc_140017EF7
0x140017ee7  mov     rcx, [rsi]; unsigned __int16 *
0x140017eea  mov     r8, r15; unsigned __int16 *
0x140017eed  mov     rdx, rdi; unsigned __int64
0x140017ef0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140017ef5  mov     ebx, eax
0x140017ef7  lea     rcx, [r14+70h]; lpCriticalSection
0x140017efb  call    cs:__imp_EnterCriticalSection
0x140017f01  cmp     dword ptr [r14+68h], 0
0x140017f06  jz      short loc_140017F2B
0x140017f08  mov     rax, [r14+20h]
0x140017f0c  test    ebx, ebx
0x140017f0e  js      short loc_140017F15
0x140017f10  mov     rcx, [rsi]
0x140017f13  jmp     short loc_140017F17
0x140017f15  xor     ecx, ecx; unsigned __int16 *
0x140017f17  mov     r8, r12; struct _DEVPROPERTY *
0x140017f1a  mov     [rsp+78h+var_58], rax; void *
0x140017f1f  mov     edx, r13d; unsigned int
0x140017f22  call    ?OnInitOobAssociationCompleteStub@@YAJPEBGKPEAU_DEVPROPERTY@@JPEAX@Z; OnInitOobAssociationCompleteStub(ushort const *,ulong,_DEVPROPERTY *,long,void *)
0x140017f27  mov     ebx, eax
0x140017f29  jmp     short loc_140017F30
0x140017f2b  mov     ebx, 80640013h
0x140017f30  lea     rcx, [r14+70h]; lpCriticalSection
0x140017f34  call    cs:__imp_LeaveCriticalSection
0x140017f3a  mov     eax, ebx
0x140017f3c  add     rsp, 38h
0x140017f40  pop     r15
0x140017f42  pop     r14
0x140017f44  pop     r13
0x140017f46  pop     r12
0x140017f48  pop     rdi
0x140017f49  pop     rsi
0x140017f4a  pop     rbp
0x140017f4b  pop     rbx
0x140017f4c  retn
```
