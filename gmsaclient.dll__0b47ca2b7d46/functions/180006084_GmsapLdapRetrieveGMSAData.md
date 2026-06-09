# GmsapLdapRetrieveGMSAData

- ea: `0x180006084`
- end: `0x180006278`
- name: `GmsapLdapRetrieveGMSAData`
- size: `500`
- prototype: `__int64 __fastcall(LDAP *ld)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003200`

## callees

- `0x180004bbc`
- `0x180006084`
- `0x180006280`
- `0x1800062b0`
- `0x18000634c`
- `0x180006a38`
- `0x180007064`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006230`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006230`
- `netutils!NetApiBufferFree` at `0x1800061fe`
- `netutils!NetApiBufferFree` at `0x1800061fe`

## pseudocode

```c
__int64 __fastcall GmsapLdapRetrieveGMSAData(LDAP *ld, __int64 a2, unsigned int *a3, unsigned __int8 **a4)
{
  unsigned __int8 *v4; // rdi
  int AccountObject; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  _UNKNOWN **v12; // rcx
  int v13; // edx
  int v14; // r9d
  int SingleBinaryAttribute; // eax
  __int64 v16; // rax
  unsigned __int8 *v17; // rcx
  size_t Size; // [rsp+30h] [rbp-20h] BYREF
  LPVOID Buffer; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *Src; // [rsp+40h] [rbp-10h] BYREF

  v4 = 0;
  Src = 0;
  Buffer = 0;
  Size = 0x100000000LL;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x3Cu, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  AccountObject = GmsapGetAccountObject(ld, a2, &Buffer, (int *)&Size + 1);
  v11 = AccountObject;
  if ( AccountObject >= 0 )
  {
    SingleBinaryAttribute = GmsapGetSingleBinaryAttribute(ld, (PWSTR)Buffer, v10, (ULONG *)&Size, &Src);
    v11 = SingleBinaryAttribute;
    if ( SingleBinaryAttribute < 0 )
    {
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v4 = Src;
        goto LABEL_19;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (_DWORD)Buffer,
        SingleBinaryAttribute);
      v4 = Src;
      goto LABEL_18;
    }
    v4 = Src;
    AccountObject = GmsapParsePasswordData((unsigned int)Size, Src, a3, a4);
    v11 = AccountObject;
    if ( AccountObject >= 0 )
    {
LABEL_18:
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = (int)Buffer;
      v13 = 63;
      goto LABEL_8;
    }
  }
  else
  {
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 61;
      v14 = a2;
LABEL_8:
      WPP_SF_SD(
        (unsigned int)v12[2],
        v13,
        (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
        v14,
        AccountObject);
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( Buffer )
  {
    NetApiBufferFree(Buffer);
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    v16 = (unsigned int)Size;
    v17 = v4;
    if ( (_DWORD)Size )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    LocalFree(v4);
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_D((TRACEHANDLE)v12[2], 0x40u, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180006084  push    rbp
0x180006086  push    rbx
0x180006087  push    rsi
0x180006088  push    rdi
0x180006089  push    r12
0x18000608b  push    r14
0x18000608d  push    r15
0x18000608f  mov     rbp, rsp
0x180006092  sub     rsp, 50h
0x180006096  xor     edi, edi
0x180006098  mov     dword ptr [rbp+Size+4], 1
0x18000609f  mov     [rbp+Src], rdi
0x1800060a3  mov     r15, r9
0x1800060a6  mov     [rbp+Buffer], rdi
0x1800060aa  mov     r12, r8
0x1800060ad  mov     r14, rdx
0x1800060b0  mov     dword ptr [rbp+Size], 0
0x1800060b7  mov     rsi, rcx
0x1800060ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060c1  lea     rax, WPP_GLOBAL_Control
0x1800060c8  cmp     rcx, rax
0x1800060cb  jz      short loc_1800060E6
0x1800060cd  test    byte ptr [rcx+1Ch], 8
0x1800060d1  jz      short loc_1800060E6
0x1800060d3  mov     rcx, [rcx+10h]
0x1800060d7  lea     edx, [rdi+3Ch]
0x1800060da  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800060e1  call    WPP_SF_
0x1800060e6  lea     r9, [rbp+Size+4]
0x1800060ea  mov     rdx, r14
0x1800060ed  lea     r8, [rbp+Buffer]
0x1800060f1  mov     rcx, rsi; ld
0x1800060f4  call    GmsapGetAccountObject
0x1800060f9  mov     ebx, eax
0x1800060fb  test    eax, eax
0x1800060fd  jns     short loc_180006141
0x1800060ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180006106  lea     rsi, WPP_GLOBAL_Control
0x18000610d  cmp     rcx, rsi
0x180006110  jz      loc_1800061F2
0x180006116  test    byte ptr [rcx+1Ch], 4
0x18000611a  jz      loc_1800061F2
0x180006120  mov     edx, 3Dh ; '='
0x180006125  mov     r9, r14
0x180006128  mov     rcx, [rcx+10h]
0x18000612c  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180006133  mov     dword ptr [rsp+50h+var_30], eax
0x180006137  call    WPP_SF_SD
0x18000613c  jmp     loc_1800061EB
0x180006141  mov     rdx, [rbp+Buffer]; base
0x180006145  lea     rax, [rbp+Src]
0x180006149  lea     r9, [rbp+Size]
0x18000614d  mov     [rsp+50h+var_30], rax; __int64
0x180006152  mov     rcx, rsi; ld
0x180006155  call    GmsapGetSingleBinaryAttribute
0x18000615a  mov     ebx, eax
0x18000615c  test    eax, eax
0x18000615e  jns     short loc_1800061A2
0x180006160  mov     rcx, cs:WPP_GLOBAL_Control
0x180006167  lea     rsi, WPP_GLOBAL_Control
0x18000616e  cmp     rcx, rsi
0x180006171  jz      short loc_18000619C
0x180006173  test    byte ptr [rcx+1Ch], 4
0x180006177  jz      short loc_18000619C
0x180006179  mov     r9, [rbp+Buffer]
0x18000617d  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180006184  mov     rcx, [rcx+10h]
0x180006188  mov     edx, 3Eh ; '>'
0x18000618d  mov     dword ptr [rsp+50h+var_30], eax
0x180006191  call    WPP_SF_SD
0x180006196  mov     rdi, [rbp+Src]
0x18000619a  jmp     short loc_1800061EB
0x18000619c  mov     rdi, [rbp+Src]
0x1800061a0  jmp     short loc_1800061F2
0x1800061a2  mov     rdi, [rbp+Src]
0x1800061a6  mov     r9, r15; unsigned __int8 **
0x1800061a9  mov     ecx, dword ptr [rbp+Size]; Size
0x1800061ac  mov     rdx, rdi; Src
0x1800061af  mov     r8, r12; unsigned int *
0x1800061b2  call    ?GmsapParsePasswordData@@YAJKPEAEPEAKPEAPEAE@Z; GmsapParsePasswordData(ulong,uchar *,ulong *,uchar * *)
0x1800061b7  mov     ebx, eax
0x1800061b9  test    eax, eax
0x1800061bb  jns     short loc_1800061E4
0x1800061bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061c4  lea     rsi, WPP_GLOBAL_Control
0x1800061cb  cmp     rcx, rsi
0x1800061ce  jz      short loc_1800061F2
0x1800061d0  test    byte ptr [rcx+1Ch], 4
0x1800061d4  jz      short loc_1800061F2
0x1800061d6  mov     r9, [rbp+Buffer]
0x1800061da  mov     edx, 3Fh ; '?'
0x1800061df  jmp     loc_180006128
0x1800061e4  lea     rsi, WPP_GLOBAL_Control
0x1800061eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061f2  mov     rax, [rbp+Buffer]
0x1800061f6  test    rax, rax
0x1800061f9  jz      short loc_180006211
0x1800061fb  mov     rcx, rax; Buffer
0x1800061fe  call    cs:__imp_NetApiBufferFree
0x180006205  nop     dword ptr [rax+rax+00h]
0x18000620a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006211  test    rdi, rdi
0x180006214  jz      short loc_180006243
0x180006216  mov     eax, dword ptr [rbp+Size]
0x180006219  mov     rcx, rdi
0x18000621c  test    rax, rax
0x18000621f  jz      short loc_18000622D
0x180006221  mov     byte ptr [rcx], 0
0x180006224  inc     rcx
0x180006227  sub     rax, 1
0x18000622b  jnz     short loc_180006221
0x18000622d  mov     rcx, rdi; hMem
0x180006230  call    cs:__imp_LocalFree
0x180006237  nop     dword ptr [rax+rax+00h]
0x18000623c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006243  cmp     rcx, rsi
0x180006246  jz      short loc_180006266
0x180006248  test    byte ptr [rcx+1Ch], 8
0x18000624c  jz      short loc_180006266
0x18000624e  mov     rcx, [rcx+10h]
0x180006252  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180006259  mov     edx, 40h ; '@'
0x18000625e  mov     r9d, ebx
0x180006261  call    WPP_SF_D
0x180006266  mov     eax, ebx
0x180006268  add     rsp, 50h
0x18000626c  pop     r15
0x18000626e  pop     r14
0x180006270  pop     r12
0x180006272  pop     rdi
0x180006273  pop     rsi
0x180006274  pop     rbx
0x180006275  pop     rbp
0x180006276  retn
```
