# AbstractSpacemap::SmartRead(ulong,ulong)

- ea: `0x10049bf0`
- end: `0x10049dc6`
- name: `?SmartRead@AbstractSpacemap@@QAEXKK@Z`
- size: `470`
- prototype: `void __thiscall(AbstractSpacemap *__hidden this, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10010810`
- `0x1003ab80`
- `0x1003b400`
- `0x1003fbc0`
- `0x10047000`
- `0x100597a0`
- `0x1005a420`

## callees

- `0x1000f750`
- `0x10048e90`
- `0x10049bf0`
- `0x1004f130`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10049cd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10049cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10049d10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10049d10`

## pseudocode

```c
void __thiscall AbstractSpacemap::SmartRead(AbstractSpacemap *this, unsigned int a2, unsigned int a3)
{
  unsigned int Page; // eax
  unsigned int v5; // esi
  unsigned int v6; // ebx
  int v7; // edi
  unsigned int i; // ebx
  _DWORD *v9; // eax
  int v10; // eax
  _DWORD v11[6]; // [esp+10h] [ebp-50h] BYREF
  int v12[3]; // [esp+28h] [ebp-38h] BYREF
  void *Block; // [esp+34h] [ebp-2Ch]
  void *v14; // [esp+38h] [ebp-28h]
  _DWORD v15[3]; // [esp+3Ch] [ebp-24h] BYREF
  void *v16; // [esp+48h] [ebp-18h]
  void *v17; // [esp+4Ch] [ebp-14h]
  unsigned int v18; // [esp+50h] [ebp-10h]
  int v19; // [esp+5Ch] [ebp-4h]

  v15[0] = 1;
  v19 = 0;
  if ( ((a3 ^ a2) & 0xFFFFFFF8) != 0
    && a3
    && (!a2 || a2 + 1 == a3 || AbstractSpacemap::NextPage(this, a2, (struct Err *)v15) == a3)
    && (v15[0] & 8) == 0 )
  {
    Page = AbstractSpacemap::NextPage(this, a3 | 7, (struct Err *)v15);
    v5 = Page;
    v18 = Page;
    if ( Page )
    {
      if ( (v15[0] & 8) == 0 )
      {
        v6 = Page + 1;
        if ( (((_BYTE)Page + 1) & 7) != 0 )
        {
          do
          {
            if ( (*(_BYTE *)(((v6 - *((_DWORD *)this + 6)) >> 3) + *((_DWORD *)this + 4))
                & *((_BYTE *)&Bitmap::ThisBit + ((v6 - *((_DWORD *)this + 6)) & 7))) == 0 )
              break;
            ++v6;
          }
          while ( (v6 & 7) != 0 );
          v5 = v18;
        }
        if ( v6 > v5 )
        {
          v7 = *(_DWORD *)this;
          EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 112));
          for ( i = v6 - v5; i; --i )
          {
            v9 = *(_DWORD **)(*(_DWORD *)(v7 + 160) + 4 * (v5 & (*(_DWORD *)(v7 + 164) - 1)));
            if ( !v9 )
              break;
            while ( v5 != v9[3] )
            {
              v9 = (_DWORD *)v9[1];
              if ( !v9 )
                goto LABEL_21;
            }
            if ( !v9[4] )
              break;
            ++v5;
          }
LABEL_21:
          LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 112));
          if ( i && *(_DWORD *)(v7 + 72) )
          {
            v12[0] = 1;
            LOBYTE(v19) = 1;
            v11[0] = 1;
            v11[1] = 0;
            v11[2] = v7;
            v11[4] = v5;
            v11[5] = i;
            System::Schedule((struct QMsg *)&Sys, (struct Err *)v11, (struct Err *)v12);
            v10 = v12[0];
            if ( (v12[0] & 8) == 0 )
              _InterlockedIncrement((volatile signed __int32 *)(v7 + 216));
            if ( (v10 & 0xFFFFFFFE) != 0 )
            {
              if ( Block )
                operator delete[](Block);
              if ( v14 )
                operator delete[](v14);
            }
          }
        }
      }
    }
  }
  if ( (v15[0] & 0xFFFFFFFE) != 0 )
  {
    if ( v16 )
      operator delete[](v16);
    if ( v17 )
      operator delete[](v17);
  }
}

```

## disassembly

```asm
0x10049bf0  mov     edi, edi
0x10049bf2  push    ebp
0x10049bf3  mov     ebp, esp
0x10049bf5  push    0FFFFFFFFh
0x10049bf7  push    offset ?SmartRead@AbstractSpacemap@@QAEXKK@Z_SEH
0x10049bfc  mov     eax, large fs:0
0x10049c02  push    eax
0x10049c03  sub     esp, 44h
0x10049c06  push    ebx
0x10049c07  push    esi
0x10049c08  push    edi
0x10049c09  mov     eax, ___security_cookie
0x10049c0e  xor     eax, ebp
0x10049c10  push    eax
0x10049c11  lea     eax, [ebp+var_C]
0x10049c14  mov     large fs:0, eax
0x10049c1a  mov     edi, ecx
0x10049c1c  mov     [ebp+var_24], 1
0x10049c23  mov     edx, [ebp+arg_0]
0x10049c26  mov     eax, edx
0x10049c28  mov     esi, [ebp+arg_4]
0x10049c2b  xor     eax, esi
0x10049c2d  mov     [ebp+var_4], 0
0x10049c34  test    eax, 0FFFFFFF8h
0x10049c39  jz      loc_10049D89
0x10049c3f  test    esi, esi
0x10049c41  jz      loc_10049D89
0x10049c47  test    edx, edx
0x10049c49  jz      short loc_10049C64
0x10049c4b  lea     eax, [edx+1]
0x10049c4e  cmp     eax, esi
0x10049c50  jz      short loc_10049C64
0x10049c52  lea     eax, [ebp+var_24]
0x10049c55  push    eax; struct Err *
0x10049c56  push    edx; unsigned int
0x10049c57  call    ?NextPage@AbstractSpacemap@@QAEKKAAVErr@@@Z; AbstractSpacemap::NextPage(ulong,Err &)
0x10049c5c  cmp     eax, esi
0x10049c5e  jnz     loc_10049D89
0x10049c64  test    byte ptr [ebp+var_24], 8
0x10049c68  jnz     loc_10049D89
0x10049c6e  lea     eax, [ebp+var_24]
0x10049c71  or      esi, 7
0x10049c74  push    eax; struct Err *
0x10049c75  push    esi; unsigned int
0x10049c76  mov     ecx, edi; this
0x10049c78  call    ?NextPage@AbstractSpacemap@@QAEKKAAVErr@@@Z; AbstractSpacemap::NextPage(ulong,Err &)
0x10049c7d  mov     esi, eax
0x10049c7f  mov     [ebp+var_10], esi
0x10049c82  test    esi, esi
0x10049c84  jz      loc_10049D89
0x10049c8a  test    byte ptr [ebp+var_24], 8
0x10049c8e  jnz     loc_10049D89
0x10049c94  lea     ebx, [esi+1]
0x10049c97  test    bl, 7
0x10049c9a  jz      short loc_10049CC2
0x10049c9c  mov     edx, [edi+18h]
0x10049c9f  mov     esi, [edi+10h]
0x10049ca2  mov     ecx, ebx
0x10049ca4  sub     ecx, edx
0x10049ca6  mov     eax, ecx
0x10049ca8  and     ecx, 7
0x10049cab  shr     eax, 3
0x10049cae  mov     al, [eax+esi]
0x10049cb1  test    ds:?ThisBit@Bitmap@@1QBEB[ecx], al; uchar const * const Bitmap::ThisBit
0x10049cb7  jz      short loc_10049CBF
0x10049cb9  inc     ebx
0x10049cba  test    bl, 7
0x10049cbd  jnz     short loc_10049CA2
0x10049cbf  mov     esi, [ebp+var_10]
0x10049cc2  cmp     ebx, esi
0x10049cc4  jbe     loc_10049D89
0x10049cca  mov     edi, [edi]
0x10049ccc  lea     eax, [edi+70h]
0x10049ccf  push    eax; lpCriticalSection
0x10049cd0  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10049cd6  sub     ebx, esi
0x10049cd8  jz      short loc_10049D0C
0x10049cda  mov     edx, [edi+0A0h]
0x10049ce0  mov     ecx, [edi+0A4h]
0x10049ce6  lea     eax, [ecx-1]
0x10049ce9  and     eax, esi
0x10049ceb  mov     eax, [edx+eax*4]
0x10049cee  test    eax, eax
0x10049cf0  jz      short loc_10049D0C
0x10049cf2  cmp     esi, [eax+0Ch]
0x10049cf5  jz      short loc_10049D00
0x10049cf7  mov     eax, [eax+4]
0x10049cfa  test    eax, eax
0x10049cfc  jnz     short loc_10049CF2
0x10049cfe  jmp     short loc_10049D0C
0x10049d00  cmp     dword ptr [eax+10h], 0
0x10049d04  jz      short loc_10049D0C
0x10049d06  inc     esi
0x10049d07  sub     ebx, 1
0x10049d0a  jnz     short loc_10049CE6
0x10049d0c  lea     eax, [edi+70h]
0x10049d0f  push    eax; lpCriticalSection
0x10049d10  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10049d16  test    ebx, ebx
0x10049d18  jz      short loc_10049D89
0x10049d1a  cmp     dword ptr [edi+48h], 0
0x10049d1e  jz      short loc_10049D89
0x10049d20  mov     [ebp+var_38], 1
0x10049d27  lea     eax, [ebp+var_38]
0x10049d2a  mov     byte ptr [ebp+var_4], 1
0x10049d2e  push    eax
0x10049d2f  lea     eax, [ebp+var_50]
0x10049d32  mov     [ebp+var_50], 1
0x10049d39  push    eax; struct Err *
0x10049d3a  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x10049d3f  mov     [ebp+var_4C], 0
0x10049d46  mov     [ebp+var_48], edi
0x10049d49  mov     [ebp+var_40], esi
0x10049d4c  mov     [ebp+var_3C], ebx
0x10049d4f  call    ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z; System::Schedule(QMsg *,Err &)
0x10049d54  mov     eax, [ebp+var_38]
0x10049d57  test    al, 8
0x10049d59  jnz     short loc_10049D62
0x10049d5b  lock inc dword ptr [edi+0D8h]
0x10049d62  test    eax, 0FFFFFFFEh
0x10049d67  jz      short loc_10049D89
0x10049d69  mov     eax, [ebp+Block]
0x10049d6c  test    eax, eax
0x10049d6e  jz      short loc_10049D79
0x10049d70  push    eax; Block
0x10049d71  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10049d76  add     esp, 4
0x10049d79  mov     eax, [ebp+var_28]
0x10049d7c  test    eax, eax
0x10049d7e  jz      short loc_10049D89
0x10049d80  push    eax; Block
0x10049d81  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10049d86  add     esp, 4
0x10049d89  test    [ebp+var_24], 0FFFFFFFEh
0x10049d90  jz      short loc_10049DB2
0x10049d92  mov     eax, [ebp+var_18]
0x10049d95  test    eax, eax
0x10049d97  jz      short loc_10049DA2
0x10049d99  push    eax; Block
0x10049d9a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10049d9f  add     esp, 4
0x10049da2  mov     eax, [ebp+var_14]
0x10049da5  test    eax, eax
0x10049da7  jz      short loc_10049DB2
0x10049da9  push    eax; Block
0x10049daa  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10049daf  add     esp, 4
0x10049db2  mov     ecx, [ebp+var_C]
0x10049db5  mov     large fs:0, ecx
0x10049dbc  pop     ecx
0x10049dbd  pop     edi
0x10049dbe  pop     esi
0x10049dbf  pop     ebx
0x10049dc0  mov     esp, ebp
0x10049dc2  pop     ebp
0x10049dc3  retn    8
0x10061590  lea     ecx, [ebp+var_24]; this
0x10061593  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061598  lea     ecx, [ebp+var_38]; this
0x1006159b  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100615a5  nop
0x100615a6  nop
0x100615a7  mov     edx, [esp-4+arg_4]
0x100615ab  lea     eax, [edx+0Ch]
0x100615ae  mov     ecx, [edx-54h]
0x100615b1  xor     ecx, eax; StackCookie
0x100615b3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100615b8  mov     eax, offset stru_10063F88
0x100615bd  jmp     ___CxxFrameHandler3
```
