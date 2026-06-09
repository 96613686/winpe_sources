# CSecuritySession::CheckForSecuritySesid(long &)

- ea: `0x10043840`
- end: `0x100438a4`
- name: `?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z`
- size: `100`
- prototype: `int __thiscall(CSecuritySession *__hidden this, int *)`
- caller_count: `13`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1003fea0`
- `0x10040610`
- `0x10040ab0`
- `0x10041060`
- `0x10041210`
- `0x100413c0`
- `0x10041890`
- `0x10041f50`
- `0x10042630`
- `0x100429a0`
- `0x10042c60`
- `0x10042ed0`
- `0x10043310`

## callees

- `0x100196e0`
- `0x10043840`

## import_xrefs

- `msjet40!__imp__JetSetSystemParameter@20` at `0x10043888`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10043888`

## pseudocode

```c
int __thiscall CSecuritySession::CheckForSecuritySesid(CSecuritySession *this, int *a2)
{
  bool v2; // zf
  int v3; // edx
  unsigned int *v4; // esi
  int result; // eax
  int v6; // edi
  int v7; // [esp+4h] [ebp-4h] BYREF

  v2 = *((_DWORD *)this + 1) == -1;
  v3 = *((_DWORD *)this + 4);
  v4 = (unsigned int *)((char *)this + 4);
  v7 = *(_DWORD *)(v3 + 96);
  if ( !v2 )
    return 0;
  result = CDataSource::JETBeginSession((JoltProperties **)v3, v4, a2);
  v6 = result;
  if ( result >= 0 )
  {
    *a2 = JetSetSystemParameter(&v7, *v4, 59, 1, 0);
    return v6;
  }
  else
  {
    *v4 = -1;
  }
  return result;
}

```

## disassembly

```asm
0x10043840  mov     edi, edi
0x10043842  push    ebp
0x10043843  mov     ebp, esp
0x10043845  push    ecx
0x10043846  cmp     dword ptr [ecx+4], 0FFFFFFFFh
0x1004384a  mov     edx, [ecx+10h]
0x1004384d  push    esi
0x1004384e  lea     esi, [ecx+4]
0x10043851  mov     eax, [edx+60h]
0x10043854  mov     [ebp+var_4], eax
0x10043857  jnz     short loc_1004389B
0x10043859  push    ebx
0x1004385a  mov     ebx, [ebp+arg_0]
0x1004385d  mov     ecx, edx; this
0x1004385f  push    edi
0x10043860  push    ebx; int *
0x10043861  push    esi; unsigned int *
0x10043862  call    ?JETBeginSession@CDataSource@@QAEJAAKAAJ@Z; CDataSource::JETBeginSession(ulong &,long &)
0x10043867  mov     edi, eax
0x10043869  test    edi, edi
0x1004386b  jns     short loc_1004387C
0x1004386d  pop     edi
0x1004386e  mov     dword ptr [esi], 0FFFFFFFFh
0x10043874  pop     ebx
0x10043875  pop     esi
0x10043876  mov     esp, ebp
0x10043878  pop     ebp
0x10043879  retn    4
0x1004387c  push    0
0x1004387e  push    1
0x10043880  push    3Bh ; ';'
0x10043882  push    dword ptr [esi]
0x10043884  lea     eax, [ebp+var_4]
0x10043887  push    eax
0x10043888  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x1004388e  mov     [ebx], eax
0x10043890  mov     eax, edi
0x10043892  pop     edi
0x10043893  pop     ebx
0x10043894  pop     esi
0x10043895  mov     esp, ebp
0x10043897  pop     ebp
0x10043898  retn    4
0x1004389b  xor     eax, eax
0x1004389d  pop     esi
0x1004389e  mov     esp, ebp
0x100438a0  pop     ebp
0x100438a1  retn    4
```
