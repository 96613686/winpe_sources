# GetPixelAspectRatio(_AMMediaType const *,long *,long *)

- ea: `0x1800130a4`
- end: `0x180013171`
- name: `?GetPixelAspectRatio@@YAJPEBU_AMMediaType@@PEAJ1@Z`
- size: `205`
- prototype: `__int64 __fastcall(const struct _AMMediaType *, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010dfc`

## callees

- `0x1800130a4`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800130e4`
- `USER32!IsRectEmpty` at `0x1800130e4`

## pseudocode

```c
__int64 __fastcall GetPixelAspectRatio(const struct _AMMediaType *a1, int *a2, int *a3)
{
  BYTE *pbFormat; // rbx
  int v6; // edx
  int v7; // r8d
  int v8; // ecx
  int v9; // eax
  int v10; // eax

  if ( *(_OWORD *)&a1->formattype == *(_OWORD *)&FORMAT_VideoInfo2 && a1->cbFormat >= 0x70 )
  {
    pbFormat = a1->pbFormat;
    if ( IsRectEmpty((const RECT *)pbFormat + 1) )
    {
      v6 = -*((_DWORD *)pbFormat + 19);
      if ( *((int *)pbFormat + 19) > 0 )
        v6 = *((_DWORD *)pbFormat + 19);
      v7 = -*((_DWORD *)pbFormat + 20);
      if ( *((int *)pbFormat + 20) > 0 )
        v7 = *((_DWORD *)pbFormat + 20);
    }
    else
    {
      v6 = *((_DWORD *)pbFormat + 6) - *((_DWORD *)pbFormat + 4);
      v7 = *((_DWORD *)pbFormat + 7) - *((_DWORD *)pbFormat + 5);
    }
    v8 = 4;
    if ( (pbFormat[64] & 4) != 0 )
    {
      v8 = 16;
      v9 = 9;
    }
    else if ( (pbFormat[64] & 2) != 0 )
    {
      v9 = 3;
    }
    else
    {
      v8 = *((_DWORD *)pbFormat + 14);
      v9 = *((_DWORD *)pbFormat + 15);
    }
    v10 = v6 * v9;
    *a2 = v7 * v8;
    *a3 = v10;
    if ( !*a2 || !v10 )
    {
      *a3 = 1;
      *a2 = 1;
    }
  }
  else
  {
    *a2 = 1;
    *a3 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800130a4  push    rbx
0x1800130a6  push    rsi
0x1800130a7  push    rdi
0x1800130a8  push    r14
0x1800130aa  sub     rsp, 28h
0x1800130ae  mov     rax, [rcx+2Ch]
0x1800130b2  mov     r14, r8
0x1800130b5  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800130bc  mov     rdi, rdx
0x1800130bf  jnz     loc_18001315B
0x1800130c5  mov     rax, [rcx+34h]
0x1800130c9  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800130d0  jnz     loc_18001315B
0x1800130d6  cmp     dword ptr [rcx+48h], 70h ; 'p'
0x1800130da  jb      short loc_18001315B
0x1800130dc  mov     rbx, [rcx+50h]
0x1800130e0  lea     rcx, [rbx+10h]; lprc
0x1800130e4  call    cs:__imp_IsRectEmpty
0x1800130ea  test    eax, eax
0x1800130ec  jz      short loc_180013105
0x1800130ee  mov     edx, [rbx+4Ch]
0x1800130f1  mov     r8d, [rbx+50h]
0x1800130f5  neg     edx
0x1800130f7  cmovs   edx, [rbx+4Ch]
0x1800130fb  neg     r8d
0x1800130fe  cmovs   r8d, [rbx+50h]
0x180013103  jmp     short loc_180013113
0x180013105  mov     edx, [rbx+18h]
0x180013108  sub     edx, [rbx+10h]
0x18001310b  mov     r8d, [rbx+1Ch]
0x18001310f  sub     r8d, [rbx+14h]
0x180013113  mov     ecx, 4
0x180013118  test    [rbx+40h], cl
0x18001311b  jz      short loc_180013127
0x18001311d  mov     ecx, 10h
0x180013122  lea     eax, [rcx-7]
0x180013125  jmp     short loc_18001313A
0x180013127  test    byte ptr [rbx+40h], 2
0x18001312b  jz      short loc_180013134
0x18001312d  mov     eax, 3
0x180013132  jmp     short loc_18001313A
0x180013134  mov     ecx, [rbx+38h]
0x180013137  mov     eax, [rbx+3Ch]
0x18001313a  imul    ecx, r8d
0x18001313e  imul    eax, edx
0x180013141  mov     [rdi], ecx
0x180013143  mov     [r14], eax
0x180013146  cmp     dword ptr [rdi], 0
0x180013149  jz      short loc_18001314F
0x18001314b  test    eax, eax
0x18001314d  jnz     short loc_180013165
0x18001314f  mov     eax, 1
0x180013154  mov     [r14], eax
0x180013157  mov     [rdi], eax
0x180013159  jmp     short loc_180013165
0x18001315b  mov     eax, 1
0x180013160  mov     [rdx], eax
0x180013162  mov     [r8], eax
0x180013165  xor     eax, eax
0x180013167  add     rsp, 28h
0x18001316b  pop     r14
0x18001316d  pop     rdi
0x18001316e  pop     rsi
0x18001316f  pop     rbx
0x180013170  retn
```
