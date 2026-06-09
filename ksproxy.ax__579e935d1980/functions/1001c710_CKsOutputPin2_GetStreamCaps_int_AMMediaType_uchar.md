# CKsOutputPin2::GetStreamCaps(int,_AMMediaType * *,uchar *)

- ea: `0x1001c710`
- end: `0x1001c7f7`
- name: `?GetStreamCaps@CKsOutputPin2@@UAGJHPAPAU_AMMediaType@@PAE@Z`
- size: `231`
- prototype: `int(CKsOutputPin2 *__hidden this, int, struct _AMMediaType **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x10017be0`
- `0x1001b4c6`
- `0x1001c710`
- `0x1001e1f8`
- `0x100302a7`
- `0x1003b5e4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001c76a`
- `ole32!CoTaskMemAlloc` at `0x1001c76a`

## pseudocode

```c
int __userpurge CKsOutputPin2::GetStreamCaps@<eax>(
        union KSDATAFORMAT *a1@<ebx>,
        struct _AMMediaType *a2@<edi>,
        CKsOutputPin *this,
        int a4,
        struct _AMMediaType **a5,
        unsigned __int8 *a6)
{
  int result; // eax
  struct _AMMediaType *v7; // eax
  int m_iCacheSize; // ecx
  int v9; // [esp+4h] [ebp-4h]

  if ( this->m_IoQueue.m_Cache.m_iUsed
    || (result = CKsOutputPin2::CreateMediaTypeArrays((CKsOutputPin2 *)((char *)&this[-1].m_CurrentInterface.Alignment
                                                                      + 12)),
        result >= 0) )
  {
    if ( this->m_MarshalerList.m_pFirst )
    {
      if ( a4 < this->m_IoQueue.m_Cache.m_iUsed )
      {
        v7 = (struct _AMMediaType *)CoTaskMemAlloc(0x48u);
        *a5 = v7;
        if ( v7 )
        {
          memset((void *)v7, 0, sizeof(struct _AMMediaType));
          v9 = ConvertKsMediaTypeToAmMediaType(a1, a2);
          if ( v9 < 0 )
          {
            DeleteMediaType((void *)*a5);
            *a5 = 0;
          }
          else
          {
            m_iCacheSize = this->m_IoQueue.m_Cache.m_iCacheSize;
            if ( m_iCacheSize && *(_DWORD *)(m_iCacheSize + 4 * a4) )
            {
              _mm_lfence();
              qmemcpy(a6, *(const void **)(this->m_IoQueue.m_Cache.m_iCacheSize + 4 * a4), 0x80u);
            }
            else
            {
              memset(a6, 0, 0x80u);
            }
          }
          return v9;
        }
        else
        {
          return -2147024882;
        }
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return CKsOutputPin::GetStreamCaps(this, a4, a5, a6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1001c710  mov     edi, edi
0x1001c712  push    ebp
0x1001c713  mov     ebp, esp
0x1001c715  push    ecx
0x1001c716  push    esi
0x1001c717  mov     esi, [ebp+arg_0]
0x1001c71a  cmp     dword ptr [esi+1FCh], 0
0x1001c721  jnz     short loc_1001C736
0x1001c723  lea     ecx, [esi-12Ch]; this
0x1001c729  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QAEJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x1001c72e  test    eax, eax
0x1001c730  js      loc_1001C7F2
0x1001c736  cmp     dword ptr [esi+1D4h], 0
0x1001c73d  jnz     short loc_1001C753
0x1001c73f  push    [ebp+arg_C]; unsigned __int8 *
0x1001c742  push    [ebp+arg_8]; struct _AMMediaType **
0x1001c745  push    [ebp+arg_4]; int
0x1001c748  push    esi; this
0x1001c749  call    ?GetStreamCaps@CKsOutputPin@@UAGJHPAPAU_AMMediaType@@PAE@Z; CKsOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)
0x1001c74e  jmp     loc_1001C7F2
0x1001c753  push    edi; struct _AMMediaType *
0x1001c754  mov     edi, [ebp+arg_4]
0x1001c757  cmp     edi, [esi+1FCh]
0x1001c75d  jl      short loc_1001C767
0x1001c75f  xor     eax, eax
0x1001c761  inc     eax
0x1001c762  jmp     loc_1001C7F1
0x1001c767  push    ebx; struct _AMMediaType *
0x1001c768  push    48h ; 'H'; cb
0x1001c76a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001c770  mov     ebx, [ebp+arg_8]
0x1001c773  mov     [ebx], eax
0x1001c775  test    eax, eax
0x1001c777  jnz     short loc_1001C780
0x1001c779  mov     eax, 8007000Eh
0x1001c77e  jmp     short loc_1001C7F0
0x1001c780  push    48h ; 'H'; Size
0x1001c782  push    0; Val
0x1001c784  push    eax; void *
0x1001c785  call    _memset
0x1001c78a  mov     ecx, [esi+1F4h]
0x1001c790  add     esp, 0Ch
0x1001c793  mov     edx, [ebx]
0x1001c795  mov     ecx, [ecx+edi*4]
0x1001c798  call    ?ConvertKsMediaTypeToAmMediaType@@YGJPATKSDATAFORMAT@@PAU_AMMediaType@@@Z; ConvertKsMediaTypeToAmMediaType(KSDATAFORMAT *,_AMMediaType *)
0x1001c79d  mov     ecx, eax
0x1001c79f  mov     [ebp+var_4], ecx
0x1001c7a2  test    ecx, ecx
0x1001c7a4  js      short loc_1001C7E0
0x1001c7a6  mov     ecx, [esi+1F8h]
0x1001c7ac  test    ecx, ecx
0x1001c7ae  jz      short loc_1001C7CC
0x1001c7b0  cmp     dword ptr [ecx+edi*4], 0
0x1001c7b4  jz      short loc_1001C7CC
0x1001c7b6  lfence
0x1001c7b9  mov     esi, [esi+1F8h]
0x1001c7bf  push    20h ; ' '
0x1001c7c1  pop     ecx
0x1001c7c2  mov     esi, [esi+edi*4]
0x1001c7c5  mov     edi, [ebp+arg_C]
0x1001c7c8  rep movsd
0x1001c7ca  jmp     short loc_1001C7ED
0x1001c7cc  push    80h; Size
0x1001c7d1  push    0; Val
0x1001c7d3  push    [ebp+arg_C]; void *
0x1001c7d6  call    _memset
0x1001c7db  add     esp, 0Ch
0x1001c7de  jmp     short loc_1001C7ED
0x1001c7e0  mov     ecx, [ebx]
0x1001c7e2  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001c7e7  mov     dword ptr [ebx], 0
0x1001c7ed  mov     eax, [ebp+var_4]
0x1001c7f0  pop     ebx
0x1001c7f1  pop     edi
0x1001c7f2  pop     esi
0x1001c7f3  leave
0x1001c7f4  retn    10h
```
