# Session::GetAccessMethod(Database *,Err &)

- ea: `0x100451d0`
- end: `0x10045306`
- name: `?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z`
- size: `310`
- prototype: `struct IAccMeth *__thiscall(Session *__hidden this, struct Database *, struct Err *)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x10035910`
- `0x10044340`
- `0x10052140`
- `0x10052320`
- `0x10053cc0`
- `0x10057d80`
- `0x10057dd0`

## callees

- `0x10012dd0`
- `0x100374c0`
- `0x100451d0`
- `0x1005cf30`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
struct IAccMeth *__thiscall Session::GetAccessMethod(Session *this, struct Database *a2, struct Err *a3)
{
  unsigned int v3; // edx
  Collection *v4; // edi
  int v5; // eax
  int v6; // ecx
  Transaction *v7; // esi
  unsigned int v8; // ecx
  int v9; // eax
  unsigned int v10; // eax
  int v12; // eax

  v3 = *((_DWORD *)this + 52);
  v4 = (Session *)((char *)this + 200);
  v5 = 0;
  if ( v3 )
  {
    while ( 1 )
    {
      v6 = *(_DWORD *)(*(_DWORD *)v4 + 4 * v5);
      if ( *(struct Database **)(v6 + 8) == a2 )
        break;
      if ( ++v5 >= v3 )
        goto LABEL_4;
    }
    ++*(_DWORD *)(v6 + 44);
    return (struct IAccMeth *)v6;
  }
  else
  {
LABEL_4:
    v7 = (Transaction *)operator new(0x30u);
    Transaction::Transaction(v7, 7u, a2);
    v8 = (unsigned int)this;
    v9 = *((_DWORD *)v7 + 2);
    *((_DWORD *)v7 + 10) = this;
    *((_DWORD *)v7 + 11) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 72));
    *(_DWORD *)v7 = *((_DWORD *)this + 3 * *((_DWORD *)this + 14) + 17);
    ++*((_DWORD *)v7 + 11);
    if ( (*(_BYTE *)a3 & 8) != 0
      || (v10 = *((_DWORD *)v4 + 2), v10 >= *((_DWORD *)v4 + 1))
      && (Collection::Grow(v4, v10 + 1, a3), (*(_BYTE *)a3 & 8) != 0)
      || (v8 = *((_DWORD *)v4 + 2),
          *(_DWORD *)(*(_DWORD *)v4 + 4 * v8) = v7,
          ++*((_DWORD *)v4 + 2),
          (*(_BYTE *)a3 & 8) != 0) )
    {
      if ( (*((_DWORD *)v7 + 11))-- == 1 )
      {
        v12 = 1;
        if ( *(int *)v7 < 1 )
        {
LABEL_13:
          IAccMeth::`scalar deleting destructor'(v7, v8);
        }
        else
        {
          while ( 1 )
          {
            v8 = 7 * v12;
            if ( *(_DWORD *)(*((_DWORD *)v7 + 9) + 56 * v12 - 48) )
              break;
            if ( ++v12 > *(_DWORD *)v7 )
            {
              if ( *((_DWORD *)v7 + 8) )
                return 0;
              goto LABEL_13;
            }
          }
        }
      }
      return 0;
    }
    return v7;
  }
}

```

## disassembly

```asm
0x100451d0  mov     edi, edi
0x100451d2  push    ebp
0x100451d3  mov     ebp, esp
0x100451d5  push    0FFFFFFFFh
0x100451d7  push    offset ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z_SEH
0x100451dc  mov     eax, large fs:0
0x100451e2  push    eax
0x100451e3  sub     esp, 8
0x100451e6  push    ebx
0x100451e7  push    esi
0x100451e8  push    edi
0x100451e9  mov     eax, ___security_cookie
0x100451ee  xor     eax, ebp
0x100451f0  push    eax
0x100451f1  lea     eax, [ebp+var_C]
0x100451f4  mov     large fs:0, eax
0x100451fa  mov     [ebp+var_10], ecx
0x100451fd  mov     edx, [ecx+0D0h]
0x10045203  lea     edi, [ecx+0C8h]
0x10045209  mov     ebx, [ebp+arg_0]
0x1004520c  xor     eax, eax
0x1004520e  test    edx, edx
0x10045210  jz      short loc_10045225
0x10045212  mov     esi, [edi]
0x10045214  mov     ecx, [esi+eax*4]
0x10045217  cmp     [ecx+8], ebx
0x1004521a  jz      loc_100452ED
0x10045220  inc     eax
0x10045221  cmp     eax, edx
0x10045223  jb      short loc_10045214
0x10045225  push    30h ; '0'; Size
0x10045227  call    ??2@YAPAXI@Z; operator new(uint)
0x1004522c  mov     esi, eax
0x1004522e  add     esp, 4
0x10045231  mov     [ebp+Block], esi
0x10045234  push    ebx; struct Database *
0x10045235  push    7; unsigned int
0x10045237  mov     ecx, esi; this
0x10045239  mov     [ebp+var_4], 0
0x10045240  call    ??0Transaction@@QAE@HPAVDatabase@@@Z; Transaction::Transaction(int,Database *)
0x10045245  mov     ecx, [ebp+var_10]
0x10045248  mov     eax, [esi+8]
0x1004524b  mov     [esi+28h], ecx
0x1004524e  mov     dword ptr [esi+2Ch], 0
0x10045255  lock inc dword ptr [eax+48h]
0x10045259  mov     eax, [ecx+38h]
0x1004525c  mov     ebx, [ebp+arg_4]
0x1004525f  lea     eax, [eax+eax*2]
0x10045262  mov     eax, [ecx+eax*4+44h]
0x10045266  mov     [esi], eax
0x10045268  mov     [ebp+var_4], 0FFFFFFFFh
0x1004526f  inc     dword ptr [esi+2Ch]
0x10045272  test    byte ptr [ebx], 8
0x10045275  jnz     short loc_1004529E
0x10045277  mov     eax, [edi+8]
0x1004527a  cmp     eax, [edi+4]
0x1004527d  jb      short loc_1004528E
0x1004527f  push    ebx; struct Err *
0x10045280  inc     eax
0x10045281  mov     ecx, edi; this
0x10045283  push    eax; unsigned int
0x10045284  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10045289  test    byte ptr [ebx], 8
0x1004528c  jnz     short loc_1004529E
0x1004528e  mov     ecx, [edi+8]
0x10045291  mov     eax, [edi]
0x10045293  mov     [eax+ecx*4], esi
0x10045296  inc     dword ptr [edi+8]
0x10045299  test    byte ptr [ebx], 8
0x1004529c  jz      short loc_100452D7
0x1004529e  add     dword ptr [esi+2Ch], 0FFFFFFFFh
0x100452a2  jnz     short loc_100452D5
0x100452a4  mov     edx, [esi]
0x100452a6  mov     eax, 1
0x100452ab  cmp     edx, eax
0x100452ad  jl      short loc_100452CD
0x100452af  mov     edi, [esi+24h]
0x100452b2  lea     ecx, ds:0[eax*8]
0x100452b9  sub     ecx, eax
0x100452bb  cmp     dword ptr [edi+ecx*8-30h], 0
0x100452c0  ja      short loc_100452D5
0x100452c2  inc     eax
0x100452c3  cmp     eax, edx
0x100452c5  jle     short loc_100452B2
0x100452c7  cmp     dword ptr [esi+20h], 0
0x100452cb  ja      short loc_100452D5
0x100452cd  push    ecx; unsigned int
0x100452ce  mov     ecx, esi; this
0x100452d0  call    ??_GIAccMeth@@AAEPAXI@Z; IAccMeth::`scalar deleting destructor'(uint)
0x100452d5  xor     esi, esi
0x100452d7  mov     eax, esi
0x100452d9  mov     ecx, [ebp+var_C]
0x100452dc  mov     large fs:0, ecx
0x100452e3  pop     ecx
0x100452e4  pop     edi
0x100452e5  pop     esi
0x100452e6  pop     ebx
0x100452e7  mov     esp, ebp
0x100452e9  pop     ebp
0x100452ea  retn    8
0x100452ed  inc     dword ptr [ecx+2Ch]
0x100452f0  mov     eax, ecx
0x100452f2  mov     ecx, [ebp+var_C]
0x100452f5  mov     large fs:0, ecx
0x100452fc  pop     ecx
0x100452fd  pop     edi
0x100452fe  pop     esi
0x100452ff  pop     ebx
0x10045300  mov     esp, ebp
0x10045302  pop     ebp
0x10045303  retn    8
0x10061500  push    30h ; '0'; unsigned int
0x10061502  mov     eax, [ebp+Block]
0x10061505  push    eax; Block
0x10061506  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006150b  add     esp, 8
0x1006150e  retn
0x10061514  nop
0x10061515  nop
0x10061516  mov     edx, [esp-4+arg_4]
0x1006151a  lea     eax, [edx+0Ch]
0x1006151d  mov     ecx, [edx-18h]
0x10061520  xor     ecx, eax; StackCookie
0x10061522  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061527  mov     eax, offset stru_10063F28
0x1006152c  jmp     ___CxxFrameHandler3
```
