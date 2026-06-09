# CEnumMediaTypes::Next(ulong,_AMMediaType * *,ulong *)

- ea: `0x10031400`
- end: `0x10031551`
- name: `?Next@CEnumMediaTypes@@UAGJKPAPAU_AMMediaType@@PAK@Z`
- size: `337`
- prototype: `int(CEnumMediaTypes *__hidden this, unsigned int, struct _AMMediaType **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1002d510`
- `0x1003035c`
- `0x10031400`
- `0x10033591`
- `0x1003aba0`
- `0x1003b5e4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x100314be`
- `ole32!CoTaskMemAlloc` at `0x100314be`

## pseudocode

```c
int __stdcall CEnumMediaTypes::Next(CEnumMediaTypes *this, unsigned int a2, struct _AMMediaType **a3, unsigned int *a4)
{
  CEnumMediaTypes *v4; // edi
  unsigned int v6; // ebx
  unsigned int v7; // esi
  CBasePin *m_pPin; // edi
  int m_Position; // edx
  HRESULT (__thiscall *GetMediaType)(CBasePin *, int, CMediaType *); // esi
  struct _AMMediaType *v11; // edi
  unsigned int v12; // [esp+10h] [ebp-60h]
  struct _AMMediaType **v13; // [esp+14h] [ebp-5Ch]
  _DWORD v14[19]; // [esp+20h] [ebp-50h] BYREF

  v13 = a3;
  v4 = this;
  if ( !a3 )
    return -2147467261;
  if ( CEnumMediaTypes::AreWeOutOfSync(this) == 1 )
    return -2147220989;
  v6 = a2;
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( a2 > 1 )
  {
    return -2147024809;
  }
  v7 = 0;
  v12 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      memset(v14, 0, 0x48u);
      m_pPin = v4->m_pPin;
      v14[10] = 1;
      v14[8] = 1;
      m_Position = this->m_Position;
      GetMediaType = m_pPin->GetMediaType;
      this->m_Position = m_Position + 1;
      if ( GetMediaType(m_pPin, m_Position, (CMediaType *)v14) )
        break;
      v11 = (struct _AMMediaType *)CoTaskMemAlloc(0x48u);
      *v13 = v11;
      if ( !v11 )
        break;
      qmemcpy((void *)v11, v14, sizeof(struct _AMMediaType));
      v7 = v12 + 1;
      memset(&v14[15], 0, 12);
      ++v13;
      ++v12;
      FreeMediaType((int)v14);
      v4 = this;
      if ( !--v6 )
        goto LABEL_15;
    }
    FreeMediaType((int)v14);
    v7 = v12;
  }
LABEL_15:
  if ( a4 )
    *a4 = v7;
  return v6 != 0;
}

```

## disassembly

```asm
0x10031400  mov     edi, edi
0x10031402  push    ebp
0x10031403  mov     ebp, esp
0x10031405  and     esp, 0FFFFFFF8h
0x10031408  sub     esp, 64h
0x1003140b  mov     eax, ___security_cookie
0x10031410  xor     eax, esp
0x10031412  mov     [esp+64h+var_4], eax
0x10031416  mov     eax, [ebp+arg_8]
0x10031419  mov     [esp+64h+var_5C], eax
0x1003141d  push    ebx
0x1003141e  mov     ebx, [ebp+arg_C]
0x10031421  mov     [esp+68h+var_54], ebx
0x10031425  push    esi
0x10031426  push    edi; struct _AMMediaType *
0x10031427  mov     edi, [ebp+this]
0x1003142a  mov     [esp+70h+var_58], edi
0x1003142e  test    eax, eax
0x10031430  jnz     short loc_1003143C
0x10031432  mov     eax, 80004003h
0x10031437  jmp     loc_1003153D
0x1003143c  mov     ecx, edi; this
0x1003143e  call    ?AreWeOutOfSync@CEnumMediaTypes@@AAEHXZ; CEnumMediaTypes::AreWeOutOfSync(void)
0x10031443  cmp     eax, 1
0x10031446  jnz     short loc_10031452
0x10031448  mov     eax, 80040203h
0x1003144d  jmp     loc_1003153D
0x10031452  test    ebx, ebx
0x10031454  mov     ebx, [ebp+arg_4]
0x10031457  jz      loc_1003150F
0x1003145d  mov     eax, [esp+70h+var_54]
0x10031461  mov     dword ptr [eax], 0
0x10031467  xor     esi, esi
0x10031469  mov     [esp+70h+var_60], esi
0x1003146d  test    ebx, ebx
0x1003146f  jz      loc_1003152C
0x10031475  push    48h ; 'H'; Size
0x10031477  lea     eax, [esp+74h+var_50]
0x1003147b  push    0; Val
0x1003147d  push    eax; void *
0x1003147e  call    _memset
0x10031483  mov     edi, [edi+8]
0x10031486  xor     eax, eax
0x10031488  mov     ecx, [esp+7Ch+var_58]
0x1003148c  inc     eax
0x1003148d  mov     [esp+7Ch+var_28], eax
0x10031491  add     esp, 0Ch
0x10031494  mov     [esp+70h+var_30], eax
0x10031498  mov     eax, [edi]
0x1003149a  mov     edx, [ecx+4]
0x1003149d  mov     esi, [eax+34h]
0x100314a0  lea     eax, [edx+1]
0x100314a3  mov     [ecx+4], eax
0x100314a6  lea     eax, [esp+70h+var_50]
0x100314aa  push    eax
0x100314ab  push    edx
0x100314ac  mov     ecx, esi; this
0x100314ae  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100314b4  mov     ecx, edi
0x100314b6  call    esi
0x100314b8  test    eax, eax
0x100314ba  jnz     short loc_1003151F
0x100314bc  push    48h ; 'H'; cb
0x100314be  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100314c4  mov     edi, eax
0x100314c6  mov     eax, [esp+70h+var_5C]
0x100314ca  mov     [eax], edi
0x100314cc  test    edi, edi
0x100314ce  jz      short loc_1003151F
0x100314d0  push    12h
0x100314d2  pop     ecx
0x100314d3  lea     esi, [esp+70h+var_50]
0x100314d7  add     eax, 4
0x100314da  rep movsd
0x100314dc  mov     esi, [esp+70h+var_60]
0x100314e0  xor     ecx, ecx
0x100314e2  mov     [esp+70h+var_C], ecx
0x100314e6  inc     esi
0x100314e7  mov     [esp+70h+var_10], ecx
0x100314eb  mov     [esp+70h+var_14], ecx
0x100314ef  lea     ecx, [esp+70h+var_50]
0x100314f3  mov     [esp+70h+var_5C], eax
0x100314f7  mov     [esp+70h+var_60], esi
0x100314fb  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x10031500  mov     edi, [esp+70h+var_58]
0x10031504  sub     ebx, 1
0x10031507  jnz     loc_10031475
0x1003150d  jmp     short loc_1003152C
0x1003150f  cmp     ebx, 1
0x10031512  jbe     loc_10031467
0x10031518  mov     eax, 80070057h
0x1003151d  jmp     short loc_1003153D
0x1003151f  lea     ecx, [esp+70h+var_50]
0x10031523  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x10031528  mov     esi, [esp+70h+var_60]
0x1003152c  mov     eax, [esp+70h+var_54]
0x10031530  test    eax, eax
0x10031532  jz      short loc_10031536
0x10031534  mov     [eax], esi
0x10031536  xor     eax, eax
0x10031538  test    ebx, ebx
0x1003153a  setnz   al
0x1003153d  mov     ecx, [esp+70h+var_4]
0x10031541  pop     edi
0x10031542  pop     esi
0x10031543  pop     ebx
0x10031544  xor     ecx, esp; StackCookie
0x10031546  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003154b  mov     esp, ebp
0x1003154d  pop     ebp
0x1003154e  retn    10h
```
