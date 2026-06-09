# CFtpObj::Save(IStream *,int)

- ea: `0x18001a4a0`
- end: `0x18001a63e`
- name: `?Save@CFtpObj@@UEAAJPEAUIStream@@H@Z`
- size: `414`
- prototype: `int(CFtpObj *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002240`
- `0x180002b60`
- `0x180019cf0`
- `0x18001a4a0`
- `0x18001a8b4`
- `0x1800269f4`
- `0x180026c3c`

## import_xrefs

- `SHELL32!__imp_ILSaveToStream` at `0x18001a542`
- `SHELL32!__imp_ILSaveToStream` at `0x18001a59d`
- `SHELL32!__imp_ILSaveToStream` at `0x18001a542`
- `SHELL32!__imp_ILSaveToStream` at `0x18001a59d`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a520`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a55d`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a5bb`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a520`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a55d`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a5bb`

## pseudocode

```c
HRESULT __fastcall CFtpObj::Save(CFtpObj *this, struct IStream *a2)
{
  HRESULT result; // eax
  __int64 v5; // rax
  int v6; // ecx
  int *v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  const ITEMIDLIST *v10; // rdx
  int v11; // edi
  __int64 v12; // rcx
  const ITEMIDLIST *Ptr; // rax
  int i; // edi
  int v15; // [rsp+20h] [rbp-39h] BYREF
  int v16; // [rsp+24h] [rbp-35h] BYREF
  __int128 pv; // [rsp+28h] [rbp-31h] BYREF
  int v18; // [rsp+38h] [rbp-21h]
  int pitem; // [rsp+40h] [rbp-19h] BYREF
  char v20[12]; // [rsp+44h] [rbp-15h] BYREF
  struct tagFORMATETC v21; // [rsp+50h] [rbp-9h] BYREF
  struct tagSTGMEDIUM v22; // [rsp+70h] [rbp+17h] BYREF

  result = -2147024809;
  if ( a2 )
  {
    if ( *((_DWORD *)this + 18) == 2 )
    {
      v18 = 0;
      v5 = *((_QWORD *)this + 6);
      pv = 0;
      v6 = **(_DWORD **)(*(_QWORD *)(v5 + 16) + 16LL);
      v7 = (int *)*((_QWORD *)this + 8);
      v15 = v6;
      v8 = *v7;
      LODWORD(v7) = *((_DWORD *)this + 28);
      v16 = v8;
      LODWORD(pv) = 1;
      DWORD2(pv) = (_DWORD)v7;
      result = IStream_Write(a2, &pv, 0x14u);
      if ( result >= 0 )
      {
        v9 = *((_QWORD *)this + 4);
        v10 = *(const ITEMIDLIST **)(v9 + 56);
        if ( !v10 )
          v10 = *(const ITEMIDLIST **)(v9 + 48);
        result = ILSaveToStream(a2, v10);
        if ( result >= 0 )
        {
          result = IStream_Write(a2, &v15, 4u);
          if ( result >= 0 )
          {
            v11 = 0;
            if ( v15 <= 0 )
            {
LABEL_15:
              result = IStream_Write(a2, &v16, 4u);
              if ( result >= 0 )
              {
                for ( i = 0; i < v16; ++i )
                {
                  if ( result < 0 )
                    break;
                  pitem = 0;
                  memset_0(v20, 0, 0x44u);
                  DSA_GetItem(*((HDSA *)this + 8), i, &pitem);
                  result = FormatEtcSaveToStream(a2, &v21);
                  if ( result >= 0 )
                    result = StgMediumSaveToStream(a2, &v22);
                }
              }
            }
            else
            {
              while ( result >= 0 )
              {
                v12 = *(_QWORD *)(*((_QWORD *)this + 6) + 16LL);
                if ( v12 )
                  Ptr = (const ITEMIDLIST *)DPA_GetPtr(*(HDPA *)(v12 + 16), v11);
                else
                  Ptr = 0;
                result = ILSaveToStream(a2, Ptr);
                if ( ++v11 >= v15 )
                {
                  if ( result < 0 )
                    return result;
                  goto LABEL_15;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      return -2147024875;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a4a0  mov     [rsp-8+arg_10], rbx
0x18001a4a5  push    rbp
0x18001a4a6  push    rsi
0x18001a4a7  push    rdi
0x18001a4a8  lea     rbp, [rsp-47h]
0x18001a4ad  sub     rsp, 0A0h
0x18001a4b4  mov     rax, cs:__security_cookie
0x18001a4bb  xor     rax, rsp
0x18001a4be  mov     [rbp+57h+var_20], rax
0x18001a4c2  mov     rbx, rdx
0x18001a4c5  mov     rsi, rcx
0x18001a4c8  mov     eax, 80070057h
0x18001a4cd  test    rdx, rdx
0x18001a4d0  jz      loc_18001A61F
0x18001a4d6  cmp     dword ptr [rcx+48h], 2
0x18001a4da  jnz     loc_18001A61A
0x18001a4e0  xor     eax, eax
0x18001a4e2  lea     rdx, [rbp+57h+pv]; pv
0x18001a4e6  mov     [rbp+57h+var_78], eax
0x18001a4e9  xorps   xmm0, xmm0
0x18001a4ec  mov     rax, [rcx+30h]
0x18001a4f0  mov     r8d, 14h; cb
0x18001a4f6  movups  [rbp+57h+pv], xmm0
0x18001a4fa  mov     rcx, [rax+10h]
0x18001a4fe  mov     rax, [rcx+10h]
0x18001a502  mov     ecx, [rax]
0x18001a504  mov     rax, [rsi+40h]
0x18001a508  mov     [rbp+57h+var_90], ecx
0x18001a50b  mov     ecx, [rax]
0x18001a50d  mov     eax, [rsi+70h]
0x18001a510  mov     [rbp+57h+var_8C], ecx
0x18001a513  mov     rcx, rbx; pstm
0x18001a516  mov     dword ptr [rbp+57h+pv], 1
0x18001a51d  mov     dword ptr [rbp+57h+pv+8], eax
0x18001a520  call    cs:__imp_IStream_Write
0x18001a526  test    eax, eax
0x18001a528  js      loc_18001A61F
0x18001a52e  mov     rax, [rsi+20h]
0x18001a532  mov     rdx, [rax+38h]
0x18001a536  test    rdx, rdx
0x18001a539  jnz     short loc_18001A53F
0x18001a53b  mov     rdx, [rax+30h]; pidl
0x18001a53f  mov     rcx, rbx; pstm
0x18001a542  call    cs:__imp_ILSaveToStream
0x18001a548  test    eax, eax
0x18001a54a  js      loc_18001A61F
0x18001a550  mov     r8d, 4; cb
0x18001a556  lea     rdx, [rbp+57h+var_90]; pv
0x18001a55a  mov     rcx, rbx; pstm
0x18001a55d  call    cs:__imp_IStream_Write
0x18001a563  test    eax, eax
0x18001a565  js      loc_18001A61F
0x18001a56b  xor     edi, edi
0x18001a56d  cmp     [rbp+57h+var_90], edi
0x18001a570  jle     short loc_18001A5AE
0x18001a572  test    eax, eax
0x18001a574  js      loc_18001A61F
0x18001a57a  mov     rax, [rsi+30h]
0x18001a57e  mov     rcx, [rax+10h]
0x18001a582  test    rcx, rcx
0x18001a585  jz      short loc_18001A595
0x18001a587  mov     rcx, [rcx+10h]; hdpa
0x18001a58b  movsxd  rdx, edi; i
0x18001a58e  call    DPA_GetPtr
0x18001a593  jmp     short loc_18001A597
0x18001a595  xor     eax, eax
0x18001a597  mov     rdx, rax; pidl
0x18001a59a  mov     rcx, rbx; pstm
0x18001a59d  call    cs:__imp_ILSaveToStream
0x18001a5a3  inc     edi
0x18001a5a5  cmp     edi, [rbp+57h+var_90]
0x18001a5a8  jl      short loc_18001A572
0x18001a5aa  test    eax, eax
0x18001a5ac  js      short loc_18001A61F
0x18001a5ae  mov     r8d, 4; cb
0x18001a5b4  lea     rdx, [rbp+57h+var_8C]; pv
0x18001a5b8  mov     rcx, rbx; pstm
0x18001a5bb  call    cs:__imp_IStream_Write
0x18001a5c1  test    eax, eax
0x18001a5c3  js      short loc_18001A61F
0x18001a5c5  xor     edi, edi
0x18001a5c7  cmp     [rbp+57h+var_8C], edi
0x18001a5ca  jle     short loc_18001A61F
0x18001a5cc  test    eax, eax
0x18001a5ce  js      short loc_18001A61F
0x18001a5d0  xor     edx, edx; Val
0x18001a5d2  mov     [rbp+57h+pitem], 0
0x18001a5d9  lea     rcx, [rbp+57h+var_6C]; void *
0x18001a5dd  lea     r8d, [rdx+44h]; Size
0x18001a5e1  call    memset_0
0x18001a5e6  mov     rcx, [rsi+40h]; hdsa
0x18001a5ea  lea     r8, [rbp+57h+pitem]; pitem
0x18001a5ee  mov     edx, edi; i
0x18001a5f0  call    DSA_GetItem
0x18001a5f5  lea     rdx, [rbp+57h+var_60]; struct tagFORMATETC *
0x18001a5f9  mov     rcx, rbx; pstm
0x18001a5fc  call    ?FormatEtcSaveToStream@@YAJPEAUIStream@@PEBUtagFORMATETC@@@Z; FormatEtcSaveToStream(IStream *,tagFORMATETC const *)
0x18001a601  test    eax, eax
0x18001a603  js      short loc_18001A611
0x18001a605  lea     rdx, [rbp+57h+var_40]; struct tagSTGMEDIUM *
0x18001a609  mov     rcx, rbx; pstm
0x18001a60c  call    ?StgMediumSaveToStream@@YAJPEAUIStream@@PEAUtagSTGMEDIUM@@@Z; StgMediumSaveToStream(IStream *,tagSTGMEDIUM *)
0x18001a611  inc     edi
0x18001a613  cmp     edi, [rbp+57h+var_8C]
0x18001a616  jl      short loc_18001A5CC
0x18001a618  jmp     short loc_18001A61F
0x18001a61a  mov     eax, 80070015h
0x18001a61f  mov     rcx, [rbp+57h+var_20]
0x18001a623  xor     rcx, rsp; StackCookie
0x18001a626  call    __security_check_cookie
0x18001a62b  mov     rbx, [rsp+0B0h+arg_10]
0x18001a633  add     rsp, 0A0h
0x18001a63a  pop     rdi
0x18001a63b  pop     rsi
0x18001a63c  pop     rbp
0x18001a63d  retn
```
