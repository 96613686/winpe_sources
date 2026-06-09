# CPackage::LoadMMStorage(IStorage *)

- ea: `0x180009370`
- end: `0x1800095da`
- name: `?LoadMMStorage@CPackage@@IEAAJPEAUIStorage@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(CPackage *__hidden this, LPSTORAGE pStg)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006900`

## callees

- `0x180009370`
- `0x1800098ac`
- `0x180009bc8`
- `0x180009dd8`
- `0x18000cba6`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `ole32!ReadClassStg` at `0x1800093db`
- `ole32!ReadClassStg` at `0x1800093db`

## pseudocode

```c
__int64 __fastcall CPackage::LoadMMStorage(CPackage *this, LPSTORAGE pStg)
{
  int v4; // ebx
  int v5; // eax
  struct IStream *v7[2]; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-19h] BYREF
  CLSID pclsid; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v10[26]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v11; // [rsp+90h] [rbp+27h] BYREF
  wchar_t v12; // [rsp+A0h] [rbp+37h]

  v7[0] = 0;
  pclsid = 0;
  v12 = aContents[8];
  v11 = *(_OWORD *)L"contents";
  *(_OWORD *)v10 = xmmword_1800104C8;
  *(_OWORD *)&v10[10] = *(__int128 *)((char *)&xmmword_1800104C8 + 10);
  ReadClassStg(pStg, &pclsid);
  if ( !memcmp_0(&pclsid, &CLSID_SOUNDREC, 0x10u) || !memcmp_0(&pclsid, &CLSID_OLE1SOUNDREC, 0x10u) )
  {
    if ( ((int (__fastcall *)(LPSTORAGE, _BYTE *, _QWORD, __int64, _DWORD, struct IStream **))pStg->lpVtbl->OpenStream)(
           pStg,
           v10,
           0,
           16,
           0,
           v7) < 0 )
    {
      v4 = ((__int64 (__fastcall *)(LPSTORAGE, __int128 *, _QWORD, __int64, _DWORD, struct IStream **))pStg->lpVtbl->OpenStream)(
             pStg,
             &v11,
             0,
             16,
             0,
             v7);
      if ( v4 < 0 )
        goto LABEL_17;
      v5 = CPackage::OLE2SoundRecReadFromStream(this, v7[0]);
      goto LABEL_15;
    }
    goto LABEL_11;
  }
  if ( !memcmp_0(&pclsid, &CLSID_MPlayer, 0x10u) || !memcmp_0(&pclsid, &CLSID_OLE1MPlayer, 0x10u) )
  {
    v4 = ((__int64 (__fastcall *)(LPSTORAGE, _BYTE *, _QWORD, __int64, _DWORD, struct IStream **))pStg->lpVtbl->OpenStream)(
           pStg,
           v10,
           0,
           16,
           0,
           v7);
    if ( v4 < 0 )
      goto LABEL_17;
LABEL_11:
    Buf1 = pclsid;
    v5 = CPackage::OLE1SoundRecReadFromStream(this, v7[0], &Buf1);
LABEL_15:
    v4 = v5;
    if ( v5 >= 0 )
    {
      *((_DWORD *)this + 38) = 0;
      *((_DWORD *)this + 27) = 1;
      *((_DWORD *)this + 32) = 1;
    }
    goto LABEL_17;
  }
  if ( memcmp_0(&pclsid, &CLSID_AVIFile, 0x10u) && memcmp_0(&pclsid, &CLSID_MIDFile, 0x10u) )
  {
    v4 = -2147418113;
    goto LABEL_17;
  }
  v4 = ((__int64 (__fastcall *)(LPSTORAGE, _BYTE *, _QWORD, __int64, _DWORD, struct IStream **))pStg->lpVtbl->OpenStream)(
         pStg,
         v10,
         0,
         16,
         0,
         v7);
  if ( v4 >= 0 )
  {
    v5 = CPackage::OLE2MPlayerReadFromStream(this, v7[0]);
    goto LABEL_15;
  }
LABEL_17:
  if ( v7[0] )
    ((void (__fastcall *)(struct IStream *))v7[0]->lpVtbl->Release)(v7[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009370  mov     [rsp-8+arg_10], rbx
0x180009375  push    rbp
0x180009376  push    rdi
0x180009377  push    r14
0x180009379  lea     rbp, [rsp-47h]
0x18000937e  sub     rsp, 0B0h
0x180009385  mov     rax, cs:__security_cookie
0x18000938c  xor     rax, rsp
0x18000938f  mov     [rbp+57h+var_18], rax
0x180009393  movups  xmm1, xmmword ptr cs:aContents; "contents"
0x18000939a  movzx   eax, word ptr cs:aContents+10h; ""
0x1800093a1  mov     rbx, rdx
0x1800093a4  xorps   xmm0, xmm0
0x1800093a7  mov     [rbp+57h+var_80], 0
0x1800093af  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800093b3  mov     rdi, rcx
0x1800093b6  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800093ba  movups  xmm0, cs:xmmword_1800104C8
0x1800093c1  mov     rcx, rbx; pStg
0x1800093c4  mov     [rbp+57h+var_20], ax
0x1800093c8  movups  [rbp+57h+var_30], xmm1
0x1800093cc  movups  xmm1, cs:xmmword_1800104C8+0Ah
0x1800093d3  movups  [rbp+57h+var_50], xmm0
0x1800093d7  movups  [rbp+57h+var_50+0Ah], xmm1
0x1800093db  call    cs:__imp_ReadClassStg
0x1800093e1  mov     r14d, 10h
0x1800093e7  lea     rdx, CLSID_SOUNDREC; Buf2
0x1800093ee  mov     r8d, r14d; Size
0x1800093f1  lea     rcx, [rbp+57h+pclsid]; Buf1
0x1800093f5  call    memcmp_0
0x1800093fa  test    eax, eax
0x1800093fc  jz      loc_18000951B
0x180009402  mov     r8d, r14d; Size
0x180009405  lea     rdx, CLSID_OLE1SOUNDREC; Buf2
0x18000940c  lea     rcx, [rbp+57h+pclsid]; Buf1
0x180009410  call    memcmp_0
0x180009415  test    eax, eax
0x180009417  jz      loc_18000951B
0x18000941d  mov     r8d, r14d; Size
0x180009420  lea     rdx, CLSID_MPlayer; Buf2
0x180009427  lea     rcx, [rbp+57h+pclsid]; Buf1
0x18000942b  call    memcmp_0
0x180009430  test    eax, eax
0x180009432  jz      loc_1800094CC
0x180009438  mov     r8d, r14d; Size
0x18000943b  lea     rdx, CLSID_OLE1MPlayer; Buf2
0x180009442  lea     rcx, [rbp+57h+pclsid]; Buf1
0x180009446  call    memcmp_0
0x18000944b  test    eax, eax
0x18000944d  jz      short loc_1800094CC
0x18000944f  mov     r8d, r14d; Size
0x180009452  lea     rdx, CLSID_AVIFile; Buf2
0x180009459  lea     rcx, [rbp+57h+pclsid]; Buf1
0x18000945d  call    memcmp_0
0x180009462  test    eax, eax
0x180009464  jz      short loc_180009487
0x180009466  mov     r8d, r14d; Size
0x180009469  lea     rdx, CLSID_MIDFile; Buf2
0x180009470  lea     rcx, [rbp+57h+pclsid]; Buf1
0x180009474  call    memcmp_0
0x180009479  test    eax, eax
0x18000947b  jz      short loc_180009487
0x18000947d  mov     ebx, 8000FFFFh
0x180009482  jmp     loc_1800095A3
0x180009487  mov     rax, [rbx]
0x18000948a  lea     rcx, [rbp+57h+var_80]
0x18000948e  mov     [rsp+0C0h+var_98], rcx
0x180009493  lea     rdx, [rbp+57h+var_50]
0x180009497  mov     r9d, r14d
0x18000949a  mov     [rsp+0C0h+var_A0], 0
0x1800094a2  xor     r8d, r8d
0x1800094a5  mov     rcx, rbx
0x1800094a8  mov     rax, [rax+20h]
0x1800094ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b1  mov     ebx, eax
0x1800094b3  test    eax, eax
0x1800094b5  js      loc_1800095A3
0x1800094bb  mov     rdx, [rbp+57h+var_80]; struct IStream *
0x1800094bf  mov     rcx, rdi; this
0x1800094c2  call    ?OLE2MPlayerReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::OLE2MPlayerReadFromStream(IStream *)
0x1800094c7  jmp     loc_180009585
0x1800094cc  mov     rax, [rbx]
0x1800094cf  lea     rcx, [rbp+57h+var_80]
0x1800094d3  mov     [rsp+0C0h+var_98], rcx
0x1800094d8  lea     rdx, [rbp+57h+var_50]
0x1800094dc  mov     r9d, r14d
0x1800094df  mov     [rsp+0C0h+var_A0], 0
0x1800094e7  xor     r8d, r8d
0x1800094ea  mov     rcx, rbx
0x1800094ed  mov     rax, [rax+20h]
0x1800094f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f6  mov     ebx, eax
0x1800094f8  test    eax, eax
0x1800094fa  js      loc_1800095A3
0x180009500  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x180009504  lea     r8, [rbp+57h+Buf1]; Buf1
0x180009508  mov     rdx, [rbp+57h+var_80]; struct IStream *
0x18000950c  mov     rcx, rdi; this
0x18000950f  movdqa  xmmword ptr [rbp+57h+Buf1.Data1], xmm0
0x180009514  call    ?OLE1SoundRecReadFromStream@CPackage@@IEAAJPEAUIStream@@U_GUID@@@Z; CPackage::OLE1SoundRecReadFromStream(IStream *,_GUID)
0x180009519  jmp     short loc_180009585
0x18000951b  mov     rax, [rbx]
0x18000951e  lea     rcx, [rbp+57h+var_80]
0x180009522  mov     [rsp+0C0h+var_98], rcx
0x180009527  lea     rdx, [rbp+57h+var_50]
0x18000952b  mov     r9d, r14d
0x18000952e  mov     [rsp+0C0h+var_A0], 0
0x180009536  xor     r8d, r8d
0x180009539  mov     rcx, rbx
0x18000953c  mov     rax, [rax+20h]
0x180009540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009545  test    eax, eax
0x180009547  jns     short loc_180009500
0x180009549  mov     rax, [rbx]
0x18000954c  lea     rcx, [rbp+57h+var_80]
0x180009550  mov     [rsp+0C0h+var_98], rcx
0x180009555  lea     rdx, [rbp+57h+var_30]
0x180009559  mov     r9d, r14d
0x18000955c  mov     [rsp+0C0h+var_A0], 0
0x180009564  xor     r8d, r8d
0x180009567  mov     rcx, rbx
0x18000956a  mov     rax, [rax+20h]
0x18000956e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009573  mov     ebx, eax
0x180009575  test    eax, eax
0x180009577  js      short loc_1800095A3
0x180009579  mov     rdx, [rbp+57h+var_80]; struct IStream *
0x18000957d  mov     rcx, rdi; this
0x180009580  call    ?OLE2SoundRecReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::OLE2SoundRecReadFromStream(IStream *)
0x180009585  mov     ebx, eax
0x180009587  test    eax, eax
0x180009589  js      short loc_1800095A3
0x18000958b  mov     eax, 1
0x180009590  mov     dword ptr [rdi+98h], 0
0x18000959a  mov     [rdi+6Ch], eax
0x18000959d  mov     [rdi+80h], eax
0x1800095a3  mov     rcx, [rbp+57h+var_80]
0x1800095a7  test    rcx, rcx
0x1800095aa  jz      short loc_1800095B8
0x1800095ac  mov     rax, [rcx]
0x1800095af  mov     rax, [rax+10h]
0x1800095b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b8  mov     eax, ebx
0x1800095ba  mov     rcx, [rbp+57h+var_18]
0x1800095be  xor     rcx, rsp; StackCookie
0x1800095c1  call    __security_check_cookie
0x1800095c6  mov     rbx, [rsp+0C0h+arg_10]
0x1800095ce  add     rsp, 0B0h
0x1800095d5  pop     r14
0x1800095d7  pop     rdi
0x1800095d8  pop     rbp
0x1800095d9  retn
```
