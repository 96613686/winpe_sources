# TemporaryDatabase::`scalar deleting destructor'(uint)

- ea: `0x1001f7e0`
- end: `0x1001f8fb`
- name: `??_GTemporaryDatabase@@EAEPAXI@Z`
- size: `283`
- prototype: `void *__thiscall(TemporaryDatabase *__hidden this, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1001f7e0`
- `0x1001f910`
- `0x100430f0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001f81b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001f81b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001f8c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001f8c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001f8a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001f8a4`

## pseudocode

```c
TemporaryDatabase *__thiscall TemporaryDatabase::`scalar deleting destructor'(TemporaryDatabase *this, char a2)
{
  unsigned int v3; // edi
  int v4; // esi
  PageDesc *v5; // esi
  unsigned int v7; // [esp+10h] [ebp-10h]

  *(_DWORD *)this = &TemporaryDatabase::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v3 = 0;
  v7 = 48 * *((_DWORD *)this + 38);
  if ( v7 )
  {
    do
    {
      v4 = *(_DWORD *)(v3 / 0x30 * *((_DWORD *)this + 34) + *((_DWORD *)this + 37));
      if ( v4 )
      {
        v5 = (*(_BYTE *)(((v3 % 0x30) >> 3) + v4) & *((_BYTE *)&Bitmap::ThisBit + ((v3 % 0x30) & 7))) != 0
           ? 0
           : (PageDesc *)(84 * (v3 % 0x30) + v4 + 8);
        if ( v5 )
        {
          PageDesc::RemovePageFromCache(v5);
          *((_BYTE *)v5 + 82) &= ~8u;
        }
      }
      ++v3;
    }
    while ( v3 < v7 );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 243) )
    operator delete[](*((void **)this + 243));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 996));
  Database::~Database(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x3FCu);
  return this;
}

```

## disassembly

```asm
0x1001f7e0  mov     edi, edi
0x1001f7e2  push    ebp
0x1001f7e3  mov     ebp, esp
0x1001f7e5  push    0FFFFFFFFh
0x1001f7e7  push    offset ??_GTemporaryDatabase@@EAEPAXI@Z_SEH
0x1001f7ec  mov     eax, large fs:0
0x1001f7f2  push    eax
0x1001f7f3  push    ecx
0x1001f7f4  push    ebx
0x1001f7f5  push    esi
0x1001f7f6  push    edi
0x1001f7f7  mov     eax, ___security_cookie
0x1001f7fc  xor     eax, ebp
0x1001f7fe  push    eax
0x1001f7ff  lea     eax, [ebp+var_C]
0x1001f802  mov     large fs:0, eax
0x1001f808  mov     ebx, ecx
0x1001f80a  lea     eax, [ebx+70h]
0x1001f80d  mov     [ebp+var_4], 0
0x1001f814  push    eax; lpCriticalSection
0x1001f815  mov     dword ptr [ebx], offset ??_7TemporaryDatabase@@6B@; const TemporaryDatabase::`vftable'
0x1001f81b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001f821  mov     eax, [ebx+98h]
0x1001f827  xor     edi, edi
0x1001f829  lea     eax, [eax+eax*2]
0x1001f82c  shl     eax, 4
0x1001f82f  mov     [ebp+var_10], eax
0x1001f832  test    eax, eax
0x1001f834  jz      short loc_1001F8A0
0x1001f836  nop     word ptr [eax+eax+00000000h]
0x1001f840  mov     ecx, [ebx+88h]
0x1001f846  mov     eax, 0AAAAAAABh
0x1001f84b  mul     edi
0x1001f84d  mov     eax, [ebx+94h]
0x1001f853  shr     edx, 5
0x1001f856  imul    ecx, edx
0x1001f859  mov     esi, [ecx+eax]
0x1001f85c  test    esi, esi
0x1001f85e  jz      short loc_1001F89A
0x1001f860  lea     eax, [edx+edx*2]
0x1001f863  mov     edx, edi
0x1001f865  shl     eax, 4
0x1001f868  sub     edx, eax
0x1001f86a  mov     eax, edx
0x1001f86c  mov     ecx, edx
0x1001f86e  shr     eax, 3
0x1001f871  and     ecx, 7
0x1001f874  mov     al, [eax+esi]
0x1001f877  test    ds:?ThisBit@Bitmap@@1QBEB[ecx], al; uchar const * const Bitmap::ThisBit
0x1001f87d  jz      short loc_1001F883
0x1001f87f  xor     esi, esi
0x1001f881  jmp     short loc_1001F88B
0x1001f883  imul    eax, edx, 54h ; 'T'
0x1001f886  add     esi, 8
0x1001f889  add     esi, eax
0x1001f88b  test    esi, esi
0x1001f88d  jz      short loc_1001F89A
0x1001f88f  mov     ecx, esi; this
0x1001f891  call    ?RemovePageFromCache@PageDesc@@QAEXXZ; PageDesc::RemovePageFromCache(void)
0x1001f896  and     byte ptr [esi+52h], 0F7h
0x1001f89a  inc     edi
0x1001f89b  cmp     edi, [ebp+var_10]
0x1001f89e  jb      short loc_1001F840
0x1001f8a0  lea     eax, [ebx+70h]
0x1001f8a3  push    eax; lpCriticalSection
0x1001f8a4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001f8aa  mov     eax, [ebx+3CCh]
0x1001f8b0  test    eax, eax
0x1001f8b2  jz      short loc_1001F8BD
0x1001f8b4  push    eax; Block
0x1001f8b5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001f8ba  add     esp, 4
0x1001f8bd  lea     eax, [ebx+3E4h]
0x1001f8c3  push    eax; lpCriticalSection
0x1001f8c4  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1001f8ca  mov     ecx, ebx; this
0x1001f8cc  call    ??1Database@@MAE@XZ; Database::~Database(void)
0x1001f8d1  test    [ebp+arg_0], 1
0x1001f8d5  jz      short loc_1001F8E5
0x1001f8d7  push    3FCh; unsigned int
0x1001f8dc  push    ebx; Block
0x1001f8dd  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001f8e2  add     esp, 8
0x1001f8e5  mov     eax, ebx
0x1001f8e7  mov     ecx, [ebp+var_C]
0x1001f8ea  mov     large fs:0, ecx
0x1001f8f1  pop     ecx
0x1001f8f2  pop     edi
0x1001f8f3  pop     esi
0x1001f8f4  pop     ebx
0x1001f8f5  mov     esp, ebp
0x1001f8f7  pop     ebp
0x1001f8f8  retn    4
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f9b0  nop
0x1005f9b1  nop
0x1005f9b2  mov     edx, [esp-4+arg_4]
0x1005f9b6  lea     eax, [edx+0Ch]
0x1005f9b9  mov     ecx, [edx-14h]
0x1005f9bc  xor     ecx, eax; StackCookie
0x1005f9be  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f9c3  mov     eax, offset stru_10062AD4
0x1005f9c8  jmp     ___CxxFrameHandler3
```
