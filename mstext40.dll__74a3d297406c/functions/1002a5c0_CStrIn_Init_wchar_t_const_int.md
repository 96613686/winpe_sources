# CStrIn::Init(wchar_t const *,int)

- ea: `0x1002a5c0`
- end: `0x1002a6c7`
- name: `?Init@CStrIn@@IAEXPB_WH@Z`
- size: `263`
- prototype: `void __thiscall(CStrIn *__hidden this, LPCWCH lpWideCharStr, int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1002a6d0`
- `0x1002a850`
- `0x1002a920`
- `0x1002aa10`
- `0x1002aac0`
- `0x1002ad40`
- `0x1002afa0`
- `0x1002b080`
- `0x1002b140`
- `0x1002b360`
- `0x1002b430`
- `0x1002b500`

## callees

- `0x1002a5c0`
- `0x1002df6a`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1002a615`
- `KERNEL32!WideCharToMultiByte` at `0x1002a656`
- `KERNEL32!WideCharToMultiByte` at `0x1002a68c`
- `KERNEL32!WideCharToMultiByte` at `0x1002a615`
- `KERNEL32!WideCharToMultiByte` at `0x1002a656`
- `KERNEL32!WideCharToMultiByte` at `0x1002a68c`

## pseudocode

```c
void __thiscall CStrIn::Init(CStrIn *this, LPCWCH lpWideCharStr, int cchWideChar)
{
  _BYTE *v5; // edi
  int v6; // eax
  int v7; // eax
  CHAR *v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // ecx
  LPCWCH lpWideCharStra; // [esp+Ch] [ebp+4h]

  *((_DWORD *)this + 132) = 0;
  if ( !((unsigned int)lpWideCharStr >> 16) || *(_DWORD *)this == -1 )
  {
    *((_DWORD *)this + 1) = lpWideCharStr;
  }
  else if ( cchWideChar )
  {
    v5 = (char *)this + 8;
    v6 = WideCharToMultiByte(*(_DWORD *)this, 0, lpWideCharStr, cchWideChar, (LPSTR)this + 8, 519, 0, 0);
    *((_DWORD *)this + 132) = v6;
    if ( v6 <= 0 )
    {
      lpWideCharStra = (LPCWCH)(WideCharToMultiByte(0, 0, lpWideCharStr, cchWideChar, 0, 0, 0, 0) + 1);
      v8 = (CHAR *)malloc((size_t)lpWideCharStra);
      *((_DWORD *)this + 1) = v8;
      if ( v8 )
      {
        v9 = WideCharToMultiByte(*(_DWORD *)this, 0, lpWideCharStr, cchWideChar, v8, (int)lpWideCharStra, 0, 0);
        v10 = *((_DWORD *)this + 1);
        *((_DWORD *)this + 132) = v9;
        *(_BYTE *)(v9 + v10) = 0;
        v11 = *((_DWORD *)this + 132);
        if ( !*(_BYTE *)(*((_DWORD *)this + 1) + v11 - 1) )
          *((_DWORD *)this + 132) = v11 - 1;
      }
      else
      {
        *v5 = 0;
        *((_DWORD *)this + 1) = v5;
      }
    }
    else
    {
      *((_BYTE *)this + v6 + 8) = 0;
      v7 = *((_DWORD *)this + 132);
      if ( !*((_BYTE *)this + v7 + 7) )
        *((_DWORD *)this + 132) = v7 - 1;
      *((_DWORD *)this + 1) = v5;
    }
  }
  else
  {
    *((_BYTE *)this + 8) = 0;
    *((_DWORD *)this + 1) = (char *)this + 8;
  }
}

```

## disassembly

```asm
0x1002a5c0  push    ebx
0x1002a5c1  mov     ebx, [esp+4+lpWideCharStr]
0x1002a5c5  mov     eax, ebx
0x1002a5c7  push    esi
0x1002a5c8  mov     esi, ecx
0x1002a5ca  shr     eax, 10h
0x1002a5cd  mov     dword ptr [esi+210h], 0
0x1002a5d7  test    eax, eax
0x1002a5d9  jz      loc_1002A6BF
0x1002a5df  mov     eax, [esi]
0x1002a5e1  cmp     eax, 0FFFFFFFFh
0x1002a5e4  jz      loc_1002A6BF
0x1002a5ea  push    ebp
0x1002a5eb  mov     ebp, [esp+0Ch+cchWideChar]
0x1002a5ef  test    ebp, ebp
0x1002a5f1  jnz     short loc_1002A602
0x1002a5f3  lea     eax, [esi+8]
0x1002a5f6  mov     byte ptr [eax], 0
0x1002a5f9  pop     ebp
0x1002a5fa  mov     [esi+4], eax
0x1002a5fd  pop     esi
0x1002a5fe  pop     ebx
0x1002a5ff  retn    8
0x1002a602  push    edi
0x1002a603  push    0; lpUsedDefaultChar
0x1002a605  push    0; lpDefaultChar
0x1002a607  push    207h; cbMultiByte
0x1002a60c  lea     edi, [esi+8]
0x1002a60f  push    edi; lpMultiByteStr
0x1002a610  push    ebp; cchWideChar
0x1002a611  push    ebx; lpWideCharStr
0x1002a612  push    0; dwFlags
0x1002a614  push    eax; CodePage
0x1002a615  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002a61b  mov     [esi+210h], eax
0x1002a621  test    eax, eax
0x1002a623  jle     short loc_1002A648
0x1002a625  mov     byte ptr [eax+esi+8], 0
0x1002a62a  mov     eax, [esi+210h]
0x1002a630  cmp     byte ptr [eax+esi+7], 0
0x1002a635  jnz     short loc_1002A63E
0x1002a637  dec     eax
0x1002a638  mov     [esi+210h], eax
0x1002a63e  mov     [esi+4], edi
0x1002a641  pop     edi
0x1002a642  pop     ebp
0x1002a643  pop     esi
0x1002a644  pop     ebx
0x1002a645  retn    8
0x1002a648  push    0; lpUsedDefaultChar
0x1002a64a  push    0; lpDefaultChar
0x1002a64c  push    0; cbMultiByte
0x1002a64e  push    0; lpMultiByteStr
0x1002a650  push    ebp; cchWideChar
0x1002a651  push    ebx; lpWideCharStr
0x1002a652  push    0; dwFlags
0x1002a654  push    0; CodePage
0x1002a656  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002a65c  inc     eax
0x1002a65d  push    eax; Size
0x1002a65e  mov     [esp+14h+lpWideCharStr], eax
0x1002a662  call    _malloc
0x1002a667  add     esp, 4
0x1002a66a  mov     [esi+4], eax
0x1002a66d  test    eax, eax
0x1002a66f  jnz     short loc_1002A67D
0x1002a671  mov     [edi], al
0x1002a673  mov     [esi+4], edi
0x1002a676  pop     edi
0x1002a677  pop     ebp
0x1002a678  pop     esi
0x1002a679  pop     ebx
0x1002a67a  retn    8
0x1002a67d  push    0; lpUsedDefaultChar
0x1002a67f  push    0; lpDefaultChar
0x1002a681  push    [esp+18h+lpWideCharStr]; cbMultiByte
0x1002a685  push    eax; lpMultiByteStr
0x1002a686  push    ebp; cchWideChar
0x1002a687  push    ebx; lpWideCharStr
0x1002a688  push    0; dwFlags
0x1002a68a  push    dword ptr [esi]; CodePage
0x1002a68c  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002a692  mov     ecx, [esi+4]
0x1002a695  mov     [esi+210h], eax
0x1002a69b  mov     byte ptr [eax+ecx], 0
0x1002a69f  mov     ecx, [esi+210h]
0x1002a6a5  mov     eax, [esi+4]
0x1002a6a8  cmp     byte ptr [eax+ecx-1], 0
0x1002a6ad  jnz     short loc_1002A641
0x1002a6af  pop     edi
0x1002a6b0  lea     eax, [ecx-1]
0x1002a6b3  pop     ebp
0x1002a6b4  mov     [esi+210h], eax
0x1002a6ba  pop     esi
0x1002a6bb  pop     ebx
0x1002a6bc  retn    8
0x1002a6bf  mov     [esi+4], ebx
0x1002a6c2  pop     esi
0x1002a6c3  pop     ebx
0x1002a6c4  retn    8
```
