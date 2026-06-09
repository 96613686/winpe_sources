# ceVerifyObjIdA(char const *)

- ea: `0x1800067b4`
- end: `0x18000691f`
- name: `?ceVerifyObjIdA@@YAJPEBD@Z`
- size: `363`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006760`

## callees

- `0x180005e48`
- `0x180006394`
- `0x1800064e0`
- `0x1800067b4`

## import_xrefs

- `msvcrt!strchr` at `0x1800068bd`
- `msvcrt!strchr` at `0x1800068bd`
- `msvcrt!atoi` at `0x1800068ce`
- `msvcrt!atoi` at `0x1800068e8`
- `msvcrt!atoi` at `0x1800068ce`
- `msvcrt!atoi` at `0x1800068e8`
- `msvcrt!isdigit` at `0x180006889`
- `msvcrt!isdigit` at `0x180006889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000690e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000690e`

## pseudocode

```c
__int64 __fastcall ceVerifyObjIdA(const char *a1)
{
  const char **v1; // rdi
  __int64 v2; // rcx
  unsigned int v3; // esi
  unsigned int v4; // eax
  unsigned __int8 *v5; // rax
  const char *v6; // rbx
  int v7; // r8d
  int v8; // edx
  char *v9; // rbx
  int v10; // eax
  int v11; // eax
  unsigned int v13; // [rsp+20h] [rbp-48h]
  _QWORD v14[5]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+28h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp+38h] BYREF
  void *v18; // [rsp+A8h] [rbp+40h] BYREF

  v1 = 0;
  hMem = 0;
  v15 = 0;
  v14[1] = 0;
  v18 = 0;
  v16 = 0;
  v14[0] = a1;
  v14[2] = 0;
  if ( !(unsigned int)ceEncodeObject((__int64)a1, (const char *)0x16, v14, 0, v13, (unsigned __int8 **)&hMem, &v15) )
  {
    v3 = ceHLastError();
    goto LABEL_25;
  }
  if ( !(unsigned int)ceDecodeObjectEx(v2, (const char *)0x16, (const unsigned __int8 *)hMem, v15, 0, &v18, &v16) )
  {
    v4 = ceHLastError();
    v1 = (const char **)v18;
    v3 = v4;
    goto LABEL_25;
  }
  v1 = (const char **)v18;
  v3 = -2147024809;
  v5 = (unsigned __int8 *)v14[0];
  v6 = *(const char **)v18;
  do
  {
    v7 = v5[*(_QWORD *)v18 - v14[0]];
    v8 = *v5 - v7;
    if ( v8 )
      break;
    ++v5;
  }
  while ( v7 );
  if ( !v8 )
  {
    while ( *v6 )
    {
      if ( isdigit(*(unsigned __int8 *)v6) )
      {
        ++v6;
      }
      else
      {
        if ( *v6 != 46 )
          goto LABEL_25;
        if ( v6 == *v1 )
          goto LABEL_25;
        if ( *++v6 == 46 || !*v6 )
          goto LABEL_25;
      }
    }
    v9 = strchr(*v1, 46);
    if ( v9 )
    {
      v10 = atoi(*v1);
      if ( v10 && (v11 = v10 - 1) != 0 )
      {
        if ( v11 != 1 )
          goto LABEL_25;
      }
      else if ( (unsigned int)atoi(v9 + 1) > 0x27 )
      {
        goto LABEL_25;
      }
      v3 = 0;
    }
  }
LABEL_25:
  if ( hMem )
    LocalFree(hMem);
  if ( v1 )
    LocalFree(v1);
  return v3;
}

```

## disassembly

```asm
0x1800067b4  push    rbp
0x1800067b6  push    rbx
0x1800067b7  push    rsi
0x1800067b8  push    rdi
0x1800067b9  mov     rbp, rsp
0x1800067bc  sub     rsp, 68h
0x1800067c0  xor     edi, edi
0x1800067c2  mov     [rbp+hMem], 0
0x1800067ca  lea     rax, [rbp+arg_0]
0x1800067ce  mov     [rbp+arg_0], 0
0x1800067d5  mov     [rsp+68h+var_38], rax; unsigned int *
0x1800067da  lea     r8, [rbp+var_28]; void *
0x1800067de  lea     rax, [rbp+hMem]
0x1800067e2  mov     [rbp+var_20], 0
0x1800067ea  lea     ebx, [rdi+16h]
0x1800067ed  mov     [rbp+arg_18], rdi
0x1800067f1  mov     edx, ebx; char *
0x1800067f3  mov     [rbp+arg_8], edi
0x1800067f6  xor     r9d, r9d; unsigned int
0x1800067f9  mov     [rbp+var_28], rcx
0x1800067fd  mov     [rbp+var_18], rdi
0x180006801  mov     [rsp+68h+var_40], rax; unsigned __int8 **
0x180006806  call    ?ceEncodeObject@@YAHKPEBDPEBXKHPEAPEAEPEAK@Z; ceEncodeObject(ulong,char const *,void const *,ulong,int,uchar * *,ulong *)
0x18000680b  test    eax, eax
0x18000680d  jnz     short loc_18000681B
0x18000680f  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180006814  mov     esi, eax
0x180006816  jmp     loc_1800068F5
0x18000681b  mov     r9d, [rbp+arg_0]; unsigned int
0x18000681f  lea     rax, [rbp+arg_8]
0x180006823  mov     r8, [rbp+hMem]; unsigned __int8 *
0x180006827  mov     rdx, rbx; char *
0x18000682a  mov     [rsp+68h+var_38], rax; unsigned int *
0x18000682f  lea     rax, [rbp+arg_18]
0x180006833  mov     [rsp+68h+var_40], rax; void **
0x180006838  mov     [rsp+68h+var_48], edi; unsigned int
0x18000683c  call    ?ceDecodeObjectEx@@YAHKPEBDPEBEKKPEAPEAXPEAK@Z; ceDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,void * *,ulong *)
0x180006841  test    eax, eax
0x180006843  jnz     short loc_180006855
0x180006845  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x18000684a  mov     rdi, [rbp+arg_18]
0x18000684e  mov     esi, eax
0x180006850  jmp     loc_1800068F5
0x180006855  mov     rdi, [rbp+arg_18]
0x180006859  mov     esi, 80070057h
0x18000685e  mov     rax, [rbp+var_28]
0x180006862  mov     rbx, [rdi]
0x180006865  mov     rcx, rbx
0x180006868  sub     rcx, rax
0x18000686b  movzx   edx, byte ptr [rax]
0x18000686e  movzx   r8d, byte ptr [rax+rcx]
0x180006873  sub     edx, r8d
0x180006876  jnz     short loc_180006880
0x180006878  inc     rax
0x18000687b  test    r8d, r8d
0x18000687e  jnz     short loc_18000686B
0x180006880  test    edx, edx
0x180006882  jnz     short loc_1800068F5
0x180006884  jmp     short loc_1800068AF
0x180006886  movzx   ecx, al; C
0x180006889  call    cs:__imp_isdigit
0x18000688f  test    eax, eax
0x180006891  jnz     short loc_1800068AC
0x180006893  cmp     byte ptr [rbx], 2Eh ; '.'
0x180006896  jnz     short loc_1800068F5
0x180006898  cmp     rbx, [rdi]
0x18000689b  jz      short loc_1800068F5
0x18000689d  inc     rbx
0x1800068a0  mov     al, [rbx]
0x1800068a2  cmp     al, 2Eh ; '.'
0x1800068a4  jz      short loc_1800068F5
0x1800068a6  test    al, al
0x1800068a8  jz      short loc_1800068F5
0x1800068aa  jmp     short loc_1800068AF
0x1800068ac  inc     rbx
0x1800068af  mov     al, [rbx]
0x1800068b1  test    al, al
0x1800068b3  jnz     short loc_180006886
0x1800068b5  mov     rcx, [rdi]; Str
0x1800068b8  mov     edx, 2Eh ; '.'; Val
0x1800068bd  call    cs:__imp_strchr
0x1800068c3  mov     rbx, rax
0x1800068c6  test    rax, rax
0x1800068c9  jz      short loc_1800068F5
0x1800068cb  mov     rcx, [rdi]; String
0x1800068ce  call    cs:__imp_atoi
0x1800068d4  test    eax, eax
0x1800068d6  jz      short loc_1800068E4
0x1800068d8  sub     eax, 1
0x1800068db  jz      short loc_1800068E4
0x1800068dd  cmp     eax, 1
0x1800068e0  jz      short loc_1800068F3
0x1800068e2  jmp     short loc_1800068F5
0x1800068e4  lea     rcx, [rbx+1]; String
0x1800068e8  call    cs:__imp_atoi
0x1800068ee  cmp     eax, 27h ; '''
0x1800068f1  ja      short loc_1800068F5
0x1800068f3  xor     esi, esi
0x1800068f5  cmp     [rbp+hMem], 0
0x1800068fa  jz      short loc_180006906
0x1800068fc  mov     rcx, [rbp+hMem]; hMem
0x180006900  call    cs:__imp_LocalFree
0x180006906  test    rdi, rdi
0x180006909  jz      short loc_180006914
0x18000690b  mov     rcx, rdi; hMem
0x18000690e  call    cs:__imp_LocalFree
0x180006914  mov     eax, esi
0x180006916  add     rsp, 68h
0x18000691a  pop     rdi
0x18000691b  pop     rsi
0x18000691c  pop     rbx
0x18000691d  pop     rbp
0x18000691e  retn
```
