# CSnapin::Compare(__int64,__int64,__int64,int *)

- ea: `0x18001bca0`
- end: `0x18001bd39`
- name: `?Compare@CSnapin@@UEAAJ_J00PEAH@Z`
- size: `153`
- prototype: `int(CSnapin *__hidden this, __int64, __int64, __int64, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180016a14`
- `0x180016a98`
- `0x180016ad0`
- `0x18001bca0`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18001bd1f`
- `KERNEL32!lstrcmpW` at `0x18001bd1f`

## pseudocode

```c
__int64 __fastcall CSnapin::Compare(CSnapin *this, int a2, CLogInfo *a3, CLogInfo *a4, int *a5)
{
  int v6; // eax
  unsigned __int16 *DisplayName; // rbx
  int v8; // edx
  unsigned __int16 *Description; // rax
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rdx

  switch ( *a5 )
  {
    case 0:
      DisplayName = CLogInfo::GetDisplayName(a4);
      Description = CLogInfo::GetDisplayName(a3);
      goto LABEL_10;
    case 1:
      v10 = &CLogInfo::_wszType;
      v11 = &CLogInfo::_wszType;
LABEL_11:
      v6 = lstrcmpW(v10, v11);
      goto LABEL_12;
    case 2:
      DisplayName = CLogInfo::GetDescription(a4);
      Description = CLogInfo::GetDescription(a3);
      goto LABEL_10;
    case 3:
      DisplayName = CLogInfo::GetLogSize(a4, a2);
      Description = CLogInfo::GetLogSize(a3, v8);
LABEL_10:
      v11 = DisplayName;
      v10 = Description;
      goto LABEL_11;
  }
  v6 = 0;
LABEL_12:
  *a5 = v6;
  return 0;
}

```

## disassembly

```asm
0x18001bca0  mov     [rsp+arg_0], rbx
0x18001bca5  mov     [rsp+arg_8], rsi
0x18001bcaa  push    rdi
0x18001bcab  sub     rsp, 20h
0x18001bcaf  mov     rdi, [rsp+28h+arg_20]
0x18001bcb4  mov     rsi, r8
0x18001bcb7  mov     ecx, [rdi]
0x18001bcb9  test    ecx, ecx
0x18001bcbb  jz      short loc_18001BD06
0x18001bcbd  sub     ecx, 1
0x18001bcc0  jz      short loc_18001BCFA
0x18001bcc2  sub     ecx, 1
0x18001bcc5  jz      short loc_18001BCE5
0x18001bcc7  cmp     ecx, 1
0x18001bcca  jz      short loc_18001BCD0
0x18001bccc  xor     eax, eax
0x18001bcce  jmp     short loc_18001BD25
0x18001bcd0  mov     rcx, r9; this
0x18001bcd3  call    ?GetLogSize@CLogInfo@@QEAAPEAGH@Z; CLogInfo::GetLogSize(int)
0x18001bcd8  mov     rcx, rsi; this
0x18001bcdb  mov     rbx, rax
0x18001bcde  call    ?GetLogSize@CLogInfo@@QEAAPEAGH@Z; CLogInfo::GetLogSize(int)
0x18001bce3  jmp     short loc_18001BD19
0x18001bce5  mov     rcx, r9; this
0x18001bce8  call    ?GetDescription@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDescription(void)
0x18001bced  mov     rcx, rsi; this
0x18001bcf0  mov     rbx, rax
0x18001bcf3  call    ?GetDescription@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDescription(void)
0x18001bcf8  jmp     short loc_18001BD19
0x18001bcfa  lea     rcx, ?_wszType@CLogInfo@@0PAGA; ushort near * CLogInfo::_wszType
0x18001bd01  mov     rdx, rcx
0x18001bd04  jmp     short loc_18001BD1F
0x18001bd06  mov     rcx, r9; this
0x18001bd09  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x18001bd0e  mov     rcx, rsi; this
0x18001bd11  mov     rbx, rax
0x18001bd14  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x18001bd19  mov     rdx, rbx; lpString2
0x18001bd1c  mov     rcx, rax; lpString1
0x18001bd1f  call    cs:__imp_lstrcmpW
0x18001bd25  mov     [rdi], eax
0x18001bd27  xor     eax, eax
0x18001bd29  mov     rbx, [rsp+28h+arg_0]
0x18001bd2e  mov     rsi, [rsp+28h+arg_8]
0x18001bd33  add     rsp, 20h
0x18001bd37  pop     rdi
0x18001bd38  retn
```
