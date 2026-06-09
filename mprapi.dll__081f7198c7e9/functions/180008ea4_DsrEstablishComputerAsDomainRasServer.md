# DsrEstablishComputerAsDomainRasServer

- ea: `0x180008ea4`
- end: `0x1800090bd`
- name: `DsrEstablishComputerAsDomainRasServer`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009740`

## callees

- `0x180008e4c`
- `0x180008ea4`
- `0x1800090c4`
- `0x180009350`
- `0x180053010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180008ef4`
- `msvcrt!wcsstr` at `0x180008ef4`
- `OLEAUT32!__imp_SysAllocString` at `0x180008f9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180008f9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000905f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000905f`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsGetObject` at `0x180008f70`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsGetObject` at `0x180008f70`

## string_xrefs

- `0x180008f46`: `DsrGroupAddRemoveMember entered for [%S] [%S]`
- `0x180008f80`: `DsrGroupAddRemoveMember: %x from ADsGetObject(%S)`
- `0x180008fd8`: `DsrGroupAddRemoveMember: %x from IsMember\n`
- `0x180009034`: `DsrGroupAddRemoveMember: %x from Add/Remove`

## pseudocode

```c
__int64 __fastcall DsrEstablishComputerAsDomainRasServer(const wchar_t *a1, const wchar_t *a2, int a3)
{
  int v5; // edi
  wchar_t *v6; // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  HRESULT Object; // eax
  int v11; // ebx
  OLECHAR *v12; // rdi
  BSTR v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  void *ppObject; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR lpszPathName[3]; // [rsp+38h] [rbp-18h] BYREF
  __int16 v19; // [rsp+78h] [rbp+28h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF

  v5 = (int)a1;
  v20 = 0;
  *(_OWORD *)lpszPathName = 0;
  DsrTraceEx(0, "DsrEstablish...: entered: %S, %S, %x", a1, a2, a3);
  v6 = wcsstr(a2, L"\\");
  if ( !v6 )
    return 87;
  *v6 = 0;
  v8 = DsrInit((unsigned int)lpszPathName, (_DWORD)a2, (int)v6 + 2, v5, (__int64)&v20);
  v9 = v8;
  if ( !v8 )
  {
    v19 = 0;
    ppObject = 0;
    DsrTraceEx(0, "DsrGroupAddRemoveMember entered for [%S] [%S]", lpszPathName[1], lpszPathName[0]);
    Object = ADsGetObject(lpszPathName[1], &IID_IADsGroup, &ppObject);
    v11 = Object;
    if ( Object < 0 )
    {
      v12 = 0;
      DsrTraceEx((unsigned int)Object, "DsrGroupAddRemoveMember: %x from ADsGetObject(%S)", Object, lpszPathName[1]);
LABEL_21:
      if ( ppObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
      if ( v12 )
        SysFreeString(v12);
      v16 = (unsigned __int16)v11;
      if ( (v11 & 0x1FFF0000) != 0x70000 )
        v16 = v11;
      v9 = 0;
      if ( v16 != 183 )
        v9 = v16;
      if ( v9 )
        DsrTraceEx(v9, "DsrEstablish...: %x from Add/Rem", v9);
      goto LABEL_31;
    }
    v13 = SysAllocString(lpszPathName[0]);
    v12 = v13;
    if ( !v13 )
    {
      v11 = -2147024882;
      goto LABEL_21;
    }
    v14 = (*(__int64 (__fastcall **)(void *, BSTR, __int16 *))(*(_QWORD *)ppObject + 184LL))(ppObject, v13, &v19);
    v11 = v14;
    if ( v14 < 0 )
    {
      DsrTraceEx((unsigned int)v14, "DsrGroupAddRemoveMember: %x from IsMember\n", (unsigned int)v14);
      goto LABEL_21;
    }
    if ( a3 )
    {
      if ( v19 )
        goto LABEL_17;
      v15 = (*(__int64 (__fastcall **)(void *, OLECHAR *))(*(_QWORD *)ppObject + 192LL))(ppObject, v12);
    }
    else
    {
      if ( v19 != -1 )
        goto LABEL_17;
      v15 = (*(__int64 (__fastcall **)(void *, OLECHAR *))(*(_QWORD *)ppObject + 200LL))(ppObject, v12);
    }
    v11 = v15;
LABEL_17:
    if ( v11 == 8239 )
    {
      v11 = 183;
    }
    else if ( v11 < 0 )
    {
      DsrTraceEx((unsigned int)v11, "DsrGroupAddRemoveMember: %x from Add/Remove", (unsigned int)v11);
    }
    goto LABEL_21;
  }
  DsrTraceEx(v8, "DsrEstablish...: %x from DsrInit", v8);
LABEL_31:
  DsrCleanup(lpszPathName, &v20);
  return v9;
}

```

## disassembly

```asm
0x180008ea4  mov     [rsp-18h+arg_0], rbx
0x180008ea9  mov     [rsp-18h+arg_10], rdi
0x180008eae  push    rbp
0x180008eaf  push    r14
0x180008eb1  push    r15
0x180008eb3  mov     rbp, rsp
0x180008eb6  sub     rsp, 50h
0x180008eba  mov     r14d, r8d
0x180008ebd  mov     dword ptr [rsp+50h+var_30], r8d
0x180008ec2  mov     r8, rcx
0x180008ec5  mov     rbx, rdx
0x180008ec8  mov     rdi, rcx
0x180008ecb  xorps   xmm0, xmm0
0x180008ece  mov     r9, rdx
0x180008ed1  xor     r15d, r15d
0x180008ed4  xor     ecx, ecx
0x180008ed6  mov     [rbp+arg_18], r15d
0x180008eda  lea     rdx, aDsrestablishEn; "DsrEstablish...: entered: %S, %S, %x"
0x180008ee1  movups  xmmword ptr [rbp+lpszPathName], xmm0
0x180008ee5  call    DsrTraceEx
0x180008eea  lea     rdx, SubStr; "\\"
0x180008ef1  mov     rcx, rbx; Str
0x180008ef4  call    cs:__imp_wcsstr
0x180008efa  mov     r8, rax
0x180008efd  test    rax, rax
0x180008f00  jnz     short loc_180008F0B
0x180008f02  lea     eax, [r15+57h]
0x180008f06  jmp     loc_1800090A7
0x180008f0b  mov     [rax], r15w
0x180008f0f  lea     rcx, [rbp+lpszPathName]
0x180008f13  lea     rax, [rbp+arg_18]
0x180008f17  add     r8, 2
0x180008f1b  mov     r9, rdi
0x180008f1e  mov     [rsp+50h+var_30], rax
0x180008f23  mov     rdx, rbx
0x180008f26  call    DsrInit
0x180008f2b  mov     ebx, eax
0x180008f2d  test    eax, eax
0x180008f2f  jz      short loc_180008F42
0x180008f31  mov     r8d, eax
0x180008f34  lea     rdx, aDsrestablishXF; "DsrEstablish...: %x from DsrInit"
0x180008f3b  mov     ecx, eax
0x180008f3d  jmp     loc_180009093
0x180008f42  mov     r9, [rbp+lpszPathName]
0x180008f46  lea     rdx, aDsrgroupaddrem_1; "DsrGroupAddRemoveMember entered for [%S"...
0x180008f4d  mov     r8, [rbp+lpszPathName+8]
0x180008f51  xor     ecx, ecx
0x180008f53  mov     [rbp+arg_8], r15w
0x180008f58  mov     [rbp+ppObject], r15
0x180008f5c  call    DsrTraceEx
0x180008f61  mov     rcx, [rbp+lpszPathName+8]; lpszPathName
0x180008f65  lea     r8, [rbp+ppObject]; ppObject
0x180008f69  lea     rdx, IID_IADsGroup; riid
0x180008f70  call    cs:__imp_ADsGetObject
0x180008f76  mov     ebx, eax
0x180008f78  test    eax, eax
0x180008f7a  jns     short loc_180008F99
0x180008f7c  mov     r9, [rbp+lpszPathName+8]
0x180008f80  lea     rdx, aDsrgroupaddrem_0; "DsrGroupAddRemoveMember: %x from ADsGet"...
0x180008f87  mov     r8d, eax
0x180008f8a  mov     ecx, eax
0x180008f8c  mov     rdi, r15
0x180008f8f  call    DsrTraceEx
0x180008f94  jmp     loc_180009042
0x180008f99  mov     rcx, [rbp+lpszPathName]; psz
0x180008f9d  call    cs:__imp_SysAllocString
0x180008fa3  mov     rdi, rax
0x180008fa6  test    rax, rax
0x180008fa9  jnz     short loc_180008FB5
0x180008fab  mov     ebx, 8007000Eh
0x180008fb0  jmp     loc_180009042
0x180008fb5  mov     rcx, [rbp+ppObject]
0x180008fb9  lea     r8, [rbp+arg_8]
0x180008fbd  mov     rdx, rdi
0x180008fc0  mov     rax, [rcx]
0x180008fc3  mov     rax, [rax+0B8h]
0x180008fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fcf  mov     ebx, eax
0x180008fd1  test    eax, eax
0x180008fd3  jns     short loc_180008FE3
0x180008fd5  mov     r8d, eax
0x180008fd8  lea     rdx, aDsrgroupaddrem_2; "DsrGroupAddRemoveMember: %x from IsMemb"...
0x180008fdf  mov     ecx, eax
0x180008fe1  jmp     short loc_18000903D
0x180008fe3  test    r14d, r14d
0x180008fe6  jz      short loc_180008FFF
0x180008fe8  cmp     [rbp+arg_8], r15w
0x180008fed  jnz     short loc_18000901E
0x180008fef  mov     rcx, [rbp+ppObject]
0x180008ff3  mov     rax, [rcx]
0x180008ff6  mov     rax, [rax+0C0h]
0x180008ffd  jmp     short loc_180009014
0x180008fff  cmp     [rbp+arg_8], 0FFFFh
0x180009004  jnz     short loc_18000901E
0x180009006  mov     rcx, [rbp+ppObject]
0x18000900a  mov     rax, [rcx]
0x18000900d  mov     rax, [rax+0C8h]
0x180009014  mov     rdx, rdi
0x180009017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901c  mov     ebx, eax
0x18000901e  cmp     ebx, 202Fh
0x180009024  jnz     short loc_18000902D
0x180009026  mov     ebx, 0B7h
0x18000902b  jmp     short loc_180009042
0x18000902d  test    ebx, ebx
0x18000902f  jns     short loc_180009042
0x180009031  mov     r8d, ebx
0x180009034  lea     rdx, aDsrgroupaddrem; "DsrGroupAddRemoveMember: %x from Add/Re"...
0x18000903b  mov     ecx, ebx
0x18000903d  call    DsrTraceEx
0x180009042  mov     rcx, [rbp+ppObject]
0x180009046  test    rcx, rcx
0x180009049  jz      short loc_180009057
0x18000904b  mov     rax, [rcx]
0x18000904e  mov     rax, [rax+10h]
0x180009052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009057  test    rdi, rdi
0x18000905a  jz      short loc_180009065
0x18000905c  mov     rcx, rdi; bstrString
0x18000905f  call    cs:__imp_SysFreeString
0x180009065  mov     eax, ebx
0x180009067  movzx   ecx, bx
0x18000906a  and     eax, 1FFF0000h
0x18000906f  cmp     eax, 70000h
0x180009074  cmovnz  ecx, ebx
0x180009077  mov     ebx, r15d
0x18000907a  cmp     ecx, 0B7h
0x180009080  cmovnz  ebx, ecx
0x180009083  test    ebx, ebx
0x180009085  jz      short loc_180009098
0x180009087  mov     r8d, ebx
0x18000908a  lea     rdx, aDsrestablishXF_0; "DsrEstablish...: %x from Add/Rem"
0x180009091  mov     ecx, ebx
0x180009093  call    DsrTraceEx
0x180009098  lea     rdx, [rbp+arg_18]
0x18000909c  lea     rcx, [rbp+lpszPathName]
0x1800090a0  call    DsrCleanup
0x1800090a5  mov     eax, ebx
0x1800090a7  lea     r11, [rsp+50h+var_s0]
0x1800090ac  mov     rbx, [r11+20h]
0x1800090b0  mov     rdi, [r11+30h]
0x1800090b4  mov     rsp, r11
0x1800090b7  pop     r15
0x1800090b9  pop     r14
0x1800090bb  pop     rbp
0x1800090bc  retn
```
