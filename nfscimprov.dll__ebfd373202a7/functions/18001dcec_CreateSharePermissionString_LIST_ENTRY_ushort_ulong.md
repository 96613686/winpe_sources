# CreateSharePermissionString(_LIST_ENTRY *,ushort * *,ulong *)

- ea: `0x18001dcec`
- end: `0x18001dfae`
- name: `?CreateSharePermissionString@@YAKPEAU_LIST_ENTRY@@PEAPEAGPEAK@Z`
- size: `706`
- prototype: `unsigned int __fastcall(struct _LIST_ENTRY *, unsigned __int16 **, unsigned int *)`
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x18001d024`
- `0x18001d798`
- `0x18001eca0`
- `0x180020920`
- `0x180020b64`

## callees

- `0x180006a54`
- `0x180006a8c`
- `0x18001dcec`
- `0x180020f98`
- `0x1800210fc`
- `0x180021600`
- `0x1800219fc`
- `0x180021af0`
- `0x180024f40`
- `0x180026a4c`
- `0x180035b40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001de49`
- `KERNEL32!HeapFree` at `0x18001df4b`
- `KERNEL32!HeapFree` at `0x18001de49`
- `KERNEL32!HeapFree` at `0x18001df4b`
- `KERNEL32!HeapAlloc` at `0x18001dd94`
- `KERNEL32!HeapAlloc` at `0x18001dd94`
- `KERNEL32!GetProcessHeap` at `0x18001dd81`
- `KERNEL32!GetProcessHeap` at `0x18001de3b`
- `KERNEL32!GetProcessHeap` at `0x18001df3d`
- `KERNEL32!GetProcessHeap` at `0x18001dd81`
- `KERNEL32!GetProcessHeap` at `0x18001de3b`
- `KERNEL32!GetProcessHeap` at `0x18001df3d`

## pseudocode

```c
__int64 __fastcall CreateSharePermissionString(struct _LIST_ENTRY *a1, unsigned __int16 **a2, unsigned int *a3)
{
  struct _LIST_ENTRY *Flink; // rax
  unsigned int *v4; // r15
  unsigned __int16 **v5; // r14
  int v7; // esi
  unsigned __int64 v8; // rax
  unsigned int IpAddressString; // edi
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // rcx
  struct _LIST_ENTRY *v14; // r14
  struct _LIST_ENTRY *v15; // rsi
  struct _LIST_ENTRY *v16; // rcx
  bool v17; // zf
  int Flink_high; // eax
  unsigned int Blink; // r13d
  char *v20; // rcx
  unsigned __int16 *v21; // rax
  unsigned int v22; // r8d
  unsigned __int16 *pcchLength; // r15
  unsigned int v24; // r11d
  HANDLE v25; // rax
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // eax
  HANDLE v30; // rax
  unsigned int v32; // eax
  unsigned __int8 v33[4]; // [rsp+40h] [rbp-C0h] BYREF
  SIZE_T dwBytes; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v36; // [rsp+58h] [rbp-A8h]
  unsigned __int16 **v37; // [rsp+60h] [rbp-A0h]
  unsigned int *v38; // [rsp+68h] [rbp-98h]
  WCHAR pStringBuf[72]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v40[1096]; // [rsp+100h] [rbp+0h] BYREF

  Flink = a1->Flink;
  v4 = a3;
  v38 = a3;
  v5 = a2;
  v37 = a2;
  v7 = 0;
  dwBytes = 0;
  while ( Flink != a1 )
  {
    Flink = Flink->Flink;
    ++v7;
  }
  if ( v7 )
    v8 = (unsigned int)(v7 << 10);
  else
    v8 = 1;
  v36 = v8;
  IpAddressString = ULongLongToULong(2 * v8, (unsigned int *)&dwBytes);
  if ( !IpAddressString )
  {
    v10 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v10);
    if ( !v12 )
      return 8;
    v35 = v12;
    *v12 = 0;
    v13 = v12;
    if ( v7 )
    {
      v14 = a1->Flink;
      while ( 1 )
      {
        do
        {
          if ( IpAddressString )
            goto LABEL_34;
          if ( v14 == a1 )
          {
            v13 = v35;
            v5 = v37;
            v4 = v38;
            goto LABEL_37;
          }
          v15 = v14 - 6;
          v16 = v14;
          v17 = LODWORD(v14[-6].Flink) == 4;
          v14 = v14->Flink;
        }
        while ( v17 );
        Flink_high = HIDWORD(v16[-1].Flink);
        Blink = (unsigned int)v16[-1].Blink;
        v20 = (char *)v16[-6].Blink;
        LODWORD(dwBytes) = Flink_high;
        v21 = ConvertToWchar(v20);
        pcchLength = v21;
        if ( !v21 )
        {
          IpAddressString = 8;
          goto LABEL_34;
        }
        switch ( LODWORD(v15->Flink) )
        {
          case 1:
            IpAddressString = NfsGetIpAddressString(v21, pStringBuf, v22);
            v24 = 78;
            if ( IpAddressString )
              goto LABEL_22;
            break;
          case 2:
            if ( !IsValidGroupName(v21) )
              goto LABEL_21;
            v24 = 71;
            break;
          case 3:
            v33[0] = 0;
            IpAddressString = NfsIsNetgroupNameValid(v21, v33);
            if ( IpAddressString )
              goto LABEL_22;
            v24 = 84;
            if ( !v33[0] )
            {
LABEL_21:
              IpAddressString = 87;
              goto LABEL_22;
            }
            break;
          default:
            goto LABEL_21;
        }
        if ( LODWORD(v15->Flink) == 1
          || (v26 = StringCchCopyW(pStringBuf, 0x41u, L"00.00.00.00"), (IpAddressString = NfsGetErrorFromHr(v26)) == 0) )
        {
          v27 = dwBytes & 7;
          if ( ((v27 - 1) & 0xFFFFFFFC) != 0 || v27 == 3 || Blink > 7 )
            goto LABEL_21;
          v28 = StringCchPrintfW(v40, 0x441u, L"%c,%s,%s,%d,%d,", v24);
          IpAddressString = NfsGetErrorFromHr(v28);
          if ( !IpAddressString )
          {
            v29 = StringCchCatExW(v12, v36, v40, &v35, (size_t)pcchLength, (unsigned int)pStringBuf);
            IpAddressString = NfsGetErrorFromHr(v29);
          }
        }
LABEL_22:
        v25 = GetProcessHeap();
        HeapFree(v25, 0, pcchLength);
      }
    }
LABEL_37:
    IpAddressString = ULongLongToULong(v13 - v12, (unsigned int *)&dwBytes + 1);
    if ( IpAddressString )
    {
LABEL_34:
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v12);
    }
    else
    {
      v32 = HIDWORD(dwBytes);
      *v5 = v12;
      *v4 = v32;
    }
  }
  return IpAddressString;
}

```

## disassembly

```asm
0x18001dcec  mov     [rsp-8+arg_18], rbx
0x18001dcf1  push    rbp
0x18001dcf2  push    rsi
0x18001dcf3  push    rdi
0x18001dcf4  push    r12
0x18001dcf6  push    r13
0x18001dcf8  push    r14
0x18001dcfa  push    r15
0x18001dcfc  lea     rbp, [rsp-8A0h]
0x18001dd04  sub     rsp, 9A0h
0x18001dd0b  mov     rax, cs:__security_cookie
0x18001dd12  xor     rax, rsp
0x18001dd15  mov     [rbp+8D0h+var_40], rax
0x18001dd1c  mov     rax, [rcx]
0x18001dd1f  mov     r15, r8
0x18001dd22  mov     [rsp+9D0h+var_968], r8
0x18001dd27  mov     r14, rdx
0x18001dd2a  mov     [rsp+9D0h+var_970], rdx
0x18001dd2f  mov     r12, rcx
0x18001dd32  mov     dword ptr [rsp+9D0h+dwBytes+4], 0
0x18001dd3a  xor     esi, esi
0x18001dd3c  mov     dword ptr [rsp+9D0h+dwBytes], 0
0x18001dd44  cmp     rax, r12
0x18001dd47  jz      short loc_18001DD50
0x18001dd49  mov     rax, [rax]
0x18001dd4c  inc     esi
0x18001dd4e  jmp     short loc_18001DD44
0x18001dd50  test    esi, esi
0x18001dd52  jz      short loc_18001DD5B
0x18001dd54  mov     eax, esi
0x18001dd56  shl     eax, 0Ah
0x18001dd59  jmp     short loc_18001DD60
0x18001dd5b  mov     eax, 1
0x18001dd60  lea     rcx, [rax+rax]; unsigned __int64
0x18001dd64  mov     [rsp+9D0h+var_978], rax
0x18001dd69  lea     rdx, [rsp+9D0h+dwBytes]; unsigned int *
0x18001dd6e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001dd73  mov     edi, eax
0x18001dd75  test    eax, eax
0x18001dd77  jnz     loc_18001DF51
0x18001dd7d  mov     ebx, dword ptr [rsp+9D0h+dwBytes]
0x18001dd81  call    cs:__imp_GetProcessHeap
0x18001dd87  lea     r13d, [rdi+8]
0x18001dd8b  mov     r8d, ebx; dwBytes
0x18001dd8e  mov     rcx, rax; hHeap
0x18001dd91  mov     edx, r13d; dwFlags
0x18001dd94  call    cs:__imp_HeapAlloc
0x18001dd9a  mov     rbx, rax
0x18001dd9d  test    rax, rax
0x18001dda0  jnz     short loc_18001DDAA
0x18001dda2  mov     edi, r13d
0x18001dda5  jmp     loc_18001DF51
0x18001ddaa  xor     eax, eax
0x18001ddac  mov     [rsp+9D0h+var_980], rbx
0x18001ddb1  mov     [rbx], ax
0x18001ddb4  mov     rcx, rbx
0x18001ddb7  test    esi, esi
0x18001ddb9  jz      loc_18001DF8C
0x18001ddbf  mov     r14, [r12]
0x18001ddc3  test    edi, edi
0x18001ddc5  jnz     loc_18001DF3D
0x18001ddcb  cmp     r14, r12
0x18001ddce  jz      loc_18001DF7D
0x18001ddd4  lea     rsi, [r14-60h]
0x18001ddd8  mov     rcx, r14
0x18001dddb  cmp     dword ptr [rsi], 4
0x18001ddde  mov     r14, [r14]
0x18001dde1  jz      short loc_18001DDC3
0x18001dde3  mov     eax, [rcx-0Ch]
0x18001dde6  mov     r13d, [rcx-8]
0x18001ddea  mov     rcx, [rcx-58h]; SrcBuf
0x18001ddee  mov     dword ptr [rsp+9D0h+dwBytes], eax
0x18001ddf2  call    ?ConvertToWchar@@YAPEAGPEAD@Z; ConvertToWchar(char *)
0x18001ddf7  mov     r15, rax
0x18001ddfa  test    rax, rax
0x18001ddfd  jz      loc_18001DF38
0x18001de03  mov     edx, [rsi]
0x18001de05  sub     edx, 1
0x18001de08  jz      short loc_18001DE68
0x18001de0a  sub     edx, 1
0x18001de0d  jz      short loc_18001DE54
0x18001de0f  cmp     edx, 1
0x18001de12  jnz     short loc_18001DE36
0x18001de14  lea     rdx, [rsp+9D0h+var_990]; unsigned __int8 *
0x18001de19  mov     [rsp+9D0h+var_990], dil
0x18001de1e  mov     rcx, rax; unsigned __int16 *
0x18001de21  call    ?NfsIsNetgroupNameValid@@YAKPEBGPEAE@Z; NfsIsNetgroupNameValid(ushort const *,uchar *)
0x18001de26  mov     edi, eax
0x18001de28  test    eax, eax
0x18001de2a  jnz     short loc_18001DE3B
0x18001de2c  lea     r11d, [rax+54h]
0x18001de30  cmp     [rsp+9D0h+var_990], al
0x18001de34  jnz     short loc_18001DE81
0x18001de36  mov     edi, 57h ; 'W'
0x18001de3b  call    cs:__imp_GetProcessHeap
0x18001de41  mov     r8, r15; lpMem
0x18001de44  xor     edx, edx; dwFlags
0x18001de46  mov     rcx, rax; hHeap
0x18001de49  call    cs:__imp_HeapFree
0x18001de4f  jmp     loc_18001DDC3
0x18001de54  mov     rcx, r15; String1
0x18001de57  call    ?IsValidGroupName@@YAEPEBG@Z; IsValidGroupName(ushort const *)
0x18001de5c  test    al, al
0x18001de5e  jz      short loc_18001DE36
0x18001de60  mov     r11d, 47h ; 'G'
0x18001de66  jmp     short loc_18001DE81
0x18001de68  lea     rdx, [rsp+9D0h+pStringBuf]; pStringBuf
0x18001de6d  mov     rcx, r15; unsigned __int16 *
0x18001de70  call    ?NfsGetIpAddressString@@YAKPEBGPEAGK@Z; NfsGetIpAddressString(ushort const *,ushort *,ulong)
0x18001de75  mov     edi, eax
0x18001de77  mov     r11d, 4Eh ; 'N'
0x18001de7d  test    eax, eax
0x18001de7f  jnz     short loc_18001DE3B
0x18001de81  cmp     dword ptr [rsi], 1
0x18001de84  jz      short loc_18001DEA9
0x18001de86  lea     r8, a00000000; "00.00.00.00"
0x18001de8d  mov     edx, 41h ; 'A'; unsigned __int64
0x18001de92  lea     rcx, [rsp+9D0h+pStringBuf]; unsigned __int16 *
0x18001de97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001de9c  mov     ecx, eax; int
0x18001de9e  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001dea3  mov     edi, eax
0x18001dea5  test    eax, eax
0x18001dea7  jnz     short loc_18001DE3B
0x18001dea9  mov     edx, dword ptr [rsp+9D0h+dwBytes]
0x18001dead  mov     ecx, edx
0x18001deaf  and     ecx, 7
0x18001deb2  lea     eax, [rcx-1]
0x18001deb5  test    eax, 0FFFFFFFCh
0x18001deba  jnz     loc_18001DE36
0x18001dec0  cmp     ecx, 3
0x18001dec3  jz      loc_18001DE36
0x18001dec9  cmp     r13d, 7
0x18001decd  ja      loc_18001DE36
0x18001ded3  mov     [rsp+9D0h+var_998], r13d
0x18001ded8  lea     rax, [rsp+9D0h+pStringBuf]
0x18001dedd  mov     [rsp+9D0h+var_9A0], edx
0x18001dee1  lea     r8, aCSSDD; "%c,%s,%s,%d,%d,"
0x18001dee8  mov     qword ptr [rsp+9D0h+var_9A8], rax; unsigned int
0x18001deed  lea     rcx, [rbp+8D0h+var_8D0]; unsigned __int16 *
0x18001def1  mov     edx, 441h; unsigned __int64
0x18001def6  mov     [rsp+9D0h+pcchLength], r15; pcchLength
0x18001defb  mov     r9d, r11d
0x18001defe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001df03  mov     ecx, eax; int
0x18001df05  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001df0a  mov     edi, eax
0x18001df0c  test    eax, eax
0x18001df0e  jnz     loc_18001DE3B
0x18001df14  mov     rdx, [rsp+9D0h+var_978]; unsigned __int64
0x18001df19  lea     r9, [rsp+9D0h+var_980]; unsigned __int16 **
0x18001df1e  lea     r8, [rbp+8D0h+var_8D0]; unsigned __int16 *
0x18001df22  mov     rcx, rbx; unsigned __int16 *
0x18001df25  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001df2a  mov     ecx, eax; int
0x18001df2c  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001df31  mov     edi, eax
0x18001df33  jmp     loc_18001DE3B
0x18001df38  mov     edi, 8
0x18001df3d  call    cs:__imp_GetProcessHeap
0x18001df43  mov     r8, rbx; lpMem
0x18001df46  xor     edx, edx; dwFlags
0x18001df48  mov     rcx, rax; hHeap
0x18001df4b  call    cs:__imp_HeapFree
0x18001df51  mov     eax, edi
0x18001df53  mov     rcx, [rbp+8D0h+var_40]
0x18001df5a  xor     rcx, rsp; StackCookie
0x18001df5d  call    __security_check_cookie
0x18001df62  mov     rbx, [rsp+9D0h+arg_18]
0x18001df6a  add     rsp, 9A0h
0x18001df71  pop     r15
0x18001df73  pop     r14
0x18001df75  pop     r13
0x18001df77  pop     r12
0x18001df79  pop     rdi
0x18001df7a  pop     rsi
0x18001df7b  pop     rbp
0x18001df7c  retn
0x18001df7d  mov     rcx, [rsp+9D0h+var_980]
0x18001df82  mov     r14, [rsp+9D0h+var_970]
0x18001df87  mov     r15, [rsp+9D0h+var_968]
0x18001df8c  sub     rcx, rbx
0x18001df8f  lea     rdx, [rsp+9D0h+dwBytes+4]; unsigned int *
0x18001df94  sar     rcx, 1; unsigned __int64
0x18001df97  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001df9c  mov     edi, eax
0x18001df9e  test    eax, eax
0x18001dfa0  jnz     short loc_18001DF3D
0x18001dfa2  mov     eax, dword ptr [rsp+9D0h+dwBytes+4]
0x18001dfa6  mov     [r14], rbx
0x18001dfa9  mov     [r15], eax
0x18001dfac  jmp     short loc_18001DF51
```
