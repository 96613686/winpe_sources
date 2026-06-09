# ATL::CComObject<CMSEnumDiscRecordersObj>::CreateInstance(ATL::CComObject<CMSEnumDiscRecordersObj> * *)

- ea: `0x18000bb64`
- end: `0x18000bc5a`
- name: `?CreateInstance@?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@SAJPEAPEAV12@@Z`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000be80`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x18000bb64`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSEnumDiscRecordersObj>::CreateInstance(_QWORD *a1)
{
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  ATL::CAtlModule *v5; // rcx
  volatile signed __int32 *v6; // rsi
  signed __int32 v7; // eax
  int v8; // eax
  int v9; // ecx
  unsigned int v10; // edi
  signed __int32 v11; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = operator new(0x48u);
  v4 = v3;
  if ( v3 )
  {
    v5 = ATL::_pAtlModule;
    v3[2] = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_BYTE *)v3 + 56) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *(_QWORD *)v3 = &ATL::CComObject<CMSEnumDiscRecordersObj>::`vftable';
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
    v6 = v4 + 2;
    do
    {
      if ( *v6 == 0x7FFFFFFF )
        break;
      v7 = *v6;
    }
    while ( v7 != _InterlockedCompareExchange(v6, v7 + 1, v7) );
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v4 + 4));
    if ( v8 >= 0 )
      *((_BYTE *)v4 + 56) = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    do
    {
      if ( *v6 == 0x7FFFFFFF )
        break;
      v11 = *v6;
    }
    while ( v11 != _InterlockedCompareExchange(v6, v11 - 1, v11) );
    if ( !v10 )
      goto LABEL_20;
    (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 56LL))(v4, 1);
  }
  else
  {
    v10 = -2147024882;
  }
  v4 = 0;
LABEL_20:
  *a1 = v4;
  return v10;
}

```

## disassembly

```asm
0x18000bb64  push    rbx
0x18000bb66  push    rsi
0x18000bb67  push    rdi
0x18000bb68  push    r14
0x18000bb6a  push    r15
0x18000bb6c  sub     rsp, 20h
0x18000bb70  mov     r14, rcx
0x18000bb73  test    rcx, rcx
0x18000bb76  jnz     short loc_18000BB82
0x18000bb78  mov     eax, 80004003h
0x18000bb7d  jmp     loc_18000BC4E
0x18000bb82  mov     qword ptr [rcx], 0
0x18000bb89  mov     ecx, 48h ; 'H'; Size
0x18000bb8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb93  mov     rbx, rax
0x18000bb96  test    rax, rax
0x18000bb99  jz      loc_18000BC42
0x18000bb9f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bba6  xorps   xmm0, xmm0
0x18000bba9  mov     dword ptr [rax+8], 0
0x18000bbb0  xor     eax, eax
0x18000bbb2  movups  xmmword ptr [rbx+10h], xmm0
0x18000bbb6  movups  xmmword ptr [rbx+20h], xmm0
0x18000bbba  mov     [rbx+30h], rax
0x18000bbbe  mov     [rbx+38h], al
0x18000bbc1  mov     [rbx+40h], rax
0x18000bbc5  lea     rax, ??_7?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@6B@; const ATL::CComObject<CMSEnumDiscRecordersObj>::`vftable'
0x18000bbcc  mov     [rbx], rax
0x18000bbcf  mov     rax, [rcx]
0x18000bbd2  mov     rax, [rax+8]
0x18000bbd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbdb  lea     rsi, [rbx+8]
0x18000bbdf  mov     r15d, 7FFFFFFFh
0x18000bbe5  jmp     short loc_18000BBF0
0x18000bbe7  lea     ecx, [rax+1]
0x18000bbea  lock cmpxchg [rsi], ecx
0x18000bbee  jz      short loc_18000BBF7
0x18000bbf0  mov     eax, [rsi]
0x18000bbf2  cmp     eax, r15d
0x18000bbf5  jnz     short loc_18000BBE7
0x18000bbf7  lea     rcx, [rsi+8]; this
0x18000bbfb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000bc00  test    eax, eax
0x18000bc02  js      short loc_18000BC08
0x18000bc04  mov     byte ptr [rsi+30h], 1
0x18000bc08  xor     ecx, ecx
0x18000bc0a  test    eax, eax
0x18000bc0c  cmovs   ecx, eax
0x18000bc0f  xor     edi, edi
0x18000bc11  test    ecx, ecx
0x18000bc13  cmovs   edi, ecx
0x18000bc16  jmp     short loc_18000BC21
0x18000bc18  lea     ecx, [rax-1]
0x18000bc1b  lock cmpxchg [rsi], ecx
0x18000bc1f  jz      short loc_18000BC28
0x18000bc21  mov     eax, [rsi]
0x18000bc23  cmp     eax, r15d
0x18000bc26  jnz     short loc_18000BC18
0x18000bc28  test    edi, edi
0x18000bc2a  jz      short loc_18000BC49
0x18000bc2c  mov     rax, [rbx]
0x18000bc2f  mov     edx, 1
0x18000bc34  mov     rcx, rbx
0x18000bc37  mov     rax, [rax+38h]
0x18000bc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc40  jmp     short loc_18000BC47
0x18000bc42  mov     edi, 8007000Eh
0x18000bc47  xor     ebx, ebx
0x18000bc49  mov     [r14], rbx
0x18000bc4c  mov     eax, edi
0x18000bc4e  add     rsp, 20h
0x18000bc52  pop     r15
0x18000bc54  pop     r14
0x18000bc56  pop     rdi
0x18000bc57  pop     rsi
0x18000bc58  pop     rbx
0x18000bc59  retn
```
