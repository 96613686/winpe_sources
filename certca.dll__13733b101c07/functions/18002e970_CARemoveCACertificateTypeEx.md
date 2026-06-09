# CARemoveCACertificateTypeEx

- ea: `0x18002e970`
- end: `0x18002ea20`
- name: `CARemoveCACertificateTypeEx`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002e960`

## callees

- `0x180008400`
- `0x18002e970`
- `0x1800362f8`
- `0x180038074`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9fe`

## pseudocode

```c
__int64 __fastcall CARemoveCACertificateTypeEx(CCAInfo *this, void *a2, void *a3)
{
  unsigned __int16 *v3; // rdi
  unsigned int v5; // ecx
  int v6; // edx
  unsigned int v7; // ebx
  unsigned int CertTypeNameOrOID; // eax
  int v9; // esi
  int v10; // eax
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  hMem = a3;
  v3 = (unsigned __int16 *)a3;
  if ( !this )
  {
    v5 = 61604644;
LABEL_3:
    v6 = -2147467261;
    v7 = -2147467261;
LABEL_4:
    CSPrintErrorLineFile(v5, v6);
    return v7;
  }
  if ( !*((_DWORD *)this + 16) )
  {
    v7 = -2147467263;
    v5 = 62194468;
    v6 = -2147467263;
    goto LABEL_4;
  }
  if ( a2 )
  {
    CertTypeNameOrOID = myGetCertTypeNameOrOID(a2, (int)a2, (unsigned __int16 **)&hMem);
    v7 = CertTypeNameOrOID;
    if ( CertTypeNameOrOID )
    {
      v6 = CertTypeNameOrOID;
      v5 = 62849828;
      goto LABEL_4;
    }
    v3 = (unsigned __int16 *)hMem;
    v9 = 1;
  }
  else
  {
    v9 = 0;
    if ( !a3 )
    {
      v5 = 63308580;
      goto LABEL_3;
    }
  }
  v10 = CCAInfo::RemoveCertType((CCAProperty **)this, v3);
  v7 = v10;
  if ( v10 )
    CSPrintErrorLineFile(0x3CA0324u, v10);
  if ( v9 )
    LocalFree(v3);
  return v7;
}

```

## disassembly

```asm
0x18002e970  mov     [rsp+hMem], r8
0x18002e975  push    rbx
0x18002e976  push    rbp
0x18002e977  push    rsi
0x18002e978  push    rdi
0x18002e979  sub     rsp, 28h
0x18002e97d  mov     rdi, r8
0x18002e980  mov     rbp, rcx
0x18002e983  test    rcx, rcx
0x18002e986  jnz     short loc_18002E99B
0x18002e988  mov     ecx, 3AC0324h; unsigned int
0x18002e98d  mov     edx, 80004003h; int
0x18002e992  mov     ebx, edx
0x18002e994  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002e999  jmp     short loc_18002EA04
0x18002e99b  cmp     dword ptr [rcx+40h], 0
0x18002e99f  jnz     short loc_18002E9AF
0x18002e9a1  mov     ebx, 80004001h
0x18002e9a6  mov     ecx, 3B50324h
0x18002e9ab  mov     edx, ebx; int
0x18002e9ad  jmp     short loc_18002E994
0x18002e9af  test    rdx, rdx
0x18002e9b2  jz      short loc_18002EA0F
0x18002e9b4  lea     r8, [rsp+48h+hMem]; unsigned __int16 **
0x18002e9b9  mov     rcx, rdx; void *
0x18002e9bc  call    ?myGetCertTypeNameOrOID@@YAJPEAXHPEAPEAG@Z; myGetCertTypeNameOrOID(void *,int,ushort * *)
0x18002e9c1  mov     ebx, eax
0x18002e9c3  test    eax, eax
0x18002e9c5  jz      short loc_18002E9D0
0x18002e9c7  mov     edx, eax
0x18002e9c9  mov     ecx, 3BF0324h
0x18002e9ce  jmp     short loc_18002E994
0x18002e9d0  mov     rdi, [rsp+48h+hMem]
0x18002e9d5  mov     esi, 1
0x18002e9da  mov     rdx, rdi; unsigned __int16 *
0x18002e9dd  mov     rcx, rbp; this
0x18002e9e0  call    ?RemoveCertType@CCAInfo@@QEAAJPEBG@Z; CCAInfo::RemoveCertType(ushort const *)
0x18002e9e5  mov     ebx, eax
0x18002e9e7  test    eax, eax
0x18002e9e9  jz      short loc_18002E9F7
0x18002e9eb  mov     edx, eax; int
0x18002e9ed  mov     ecx, 3CA0324h; unsigned int
0x18002e9f2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002e9f7  test    esi, esi
0x18002e9f9  jz      short loc_18002EA04
0x18002e9fb  mov     rcx, rdi; hMem
0x18002e9fe  call    cs:__imp_LocalFree
0x18002ea04  mov     eax, ebx
0x18002ea06  add     rsp, 28h
0x18002ea0a  pop     rdi
0x18002ea0b  pop     rsi
0x18002ea0c  pop     rbp
0x18002ea0d  pop     rbx
0x18002ea0e  retn
0x18002ea0f  xor     esi, esi
0x18002ea11  test    r8, r8
0x18002ea14  jnz     short loc_18002E9DA
0x18002ea16  mov     ecx, 3C60324h
0x18002ea1b  jmp     loc_18002E98D
```
