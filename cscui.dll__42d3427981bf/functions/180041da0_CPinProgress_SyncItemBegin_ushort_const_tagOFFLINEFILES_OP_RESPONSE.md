# CPinProgress::SyncItemBegin(ushort const *,tagOFFLINEFILES_OP_RESPONSE *)

- ea: `0x180041da0`
- end: `0x180041ebf`
- name: `?SyncItemBegin@CPinProgress@@UEAAJPEBGPEAW4tagOFFLINEFILES_OP_RESPONSE@@@Z`
- size: `287`
- prototype: `int(CPinProgress *__hidden this, const unsigned __int16 *, enum tagOFFLINEFILES_OP_RESPONSE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003a90`
- `0x180003c20`
- `0x180008848`
- `0x180013dfc`
- `0x180041da0`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180041e2e`
- `SHLWAPI!PathFindFileNameW` at `0x180041e2e`
- `USER32!SendMessageW` at `0x180041e63`
- `USER32!SendMessageW` at `0x180041e63`

## pseudocode

```c
__int64 __fastcall CPinProgress::SyncItemBegin(
        CPinProgress *this,
        const unsigned __int16 *a2,
        enum tagOFFLINEFILES_OP_RESPONSE *a3)
{
  int v6; // ebx
  int v7; // edx
  LPWSTR FileNameW; // rax
  void *v9; // rdx
  void *v11; // [rsp+50h] [rbp+8h] BYREF
  LPARAM lParam; // [rsp+60h] [rbp+18h] BYREF

  *a3 = OFFLINEFILES_OP_CONTINUE;
  v11 = 0;
  if ( (int)UnMarshalFromGIT(*((_DWORD *)this + 11), &GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7, &v11) < 0
    || (v6 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, enum tagOFFLINEFILES_OP_RESPONSE *))(*(_QWORD *)v11 + 48LL))(
               v11,
               a2,
               a3),
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11),
        v6 < 0)
    || *a3 == OFFLINEFILES_OP_CONTINUE )
  {
    v7 = *((_DWORD *)this + 5);
    *a3 = v7 != 0 ? OFFLINEFILES_OP_ABORT : OFFLINEFILES_OP_CONTINUE;
    if ( !v7 )
    {
      lParam = 0;
      FileNameW = PathFindFileNameW(a2);
      if ( (int)CscUtil_FormatStringID((LPWSTR)&lParam, g_hInstance, 0x116Cu, FileNameW) >= 0 )
      {
        SendMessageW(*((HWND *)this + 3), 0x46Cu, 0, lParam);
        CscUtil_HeapFree((void *)lParam, v9);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
      (_DWORD)a2,
      *a3 == OFFLINEFILES_OP_ABORT);
  }
  return 0;
}

```

## disassembly

```asm
0x180041da0  mov     [rsp+arg_8], rbx
0x180041da5  push    rbp
0x180041da6  push    rsi
0x180041da7  push    rdi
0x180041da8  sub     rsp, 30h
0x180041dac  mov     dword ptr [r8], 0
0x180041db3  mov     rdi, r8
0x180041db6  mov     rbp, rdx
0x180041db9  mov     [rsp+48h+arg_0], 0
0x180041dc2  mov     rsi, rcx
0x180041dc5  lea     r8, [rsp+48h+arg_0]; void **
0x180041dca  mov     ecx, [rcx+2Ch]; unsigned int
0x180041dcd  lea     rdx, _GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7; struct _GUID *
0x180041dd4  call    ?UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z; UnMarshalFromGIT(ulong,_GUID const &,void * *)
0x180041dd9  test    eax, eax
0x180041ddb  js      short loc_180041E10
0x180041ddd  mov     rcx, [rsp+48h+arg_0]
0x180041de2  mov     r8, rdi
0x180041de5  mov     rdx, rbp
0x180041de8  mov     rax, [rcx]
0x180041deb  mov     rax, [rax+30h]
0x180041def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041df4  mov     rcx, [rsp+48h+arg_0]
0x180041df9  mov     ebx, eax
0x180041dfb  mov     rdx, [rcx]
0x180041dfe  mov     rax, [rdx+10h]
0x180041e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e07  test    ebx, ebx
0x180041e09  js      short loc_180041E10
0x180041e0b  cmp     dword ptr [rdi], 0
0x180041e0e  jnz     short loc_180041E73
0x180041e10  mov     edx, [rsi+14h]
0x180041e13  mov     eax, edx
0x180041e15  neg     eax
0x180041e17  sbb     ecx, ecx
0x180041e19  and     ecx, 2
0x180041e1c  mov     [rdi], ecx
0x180041e1e  test    edx, edx
0x180041e20  jnz     short loc_180041E73
0x180041e22  mov     rcx, rbp; pszPath
0x180041e25  mov     [rsp+48h+lParam], 0
0x180041e2e  call    cs:__imp_PathFindFileNameW
0x180041e34  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180041e3b  lea     rcx, [rsp+48h+lParam]; lpBuffer
0x180041e40  mov     r9, rax
0x180041e43  mov     r8d, 116Ch; uID
0x180041e49  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180041e4e  test    eax, eax
0x180041e50  js      short loc_180041E73
0x180041e52  mov     r9, [rsp+48h+lParam]; lParam
0x180041e57  xor     r8d, r8d; wParam
0x180041e5a  mov     rcx, [rsi+18h]; hWnd
0x180041e5e  mov     edx, 46Ch; Msg
0x180041e63  call    cs:__imp_SendMessageW
0x180041e69  mov     rcx, [rsp+48h+lParam]; lpMem
0x180041e6e  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180041e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e7a  lea     rax, WPP_GLOBAL_Control
0x180041e81  cmp     rcx, rax
0x180041e84  jz      short loc_180041EB0
0x180041e86  test    byte ptr [rcx+1Ch], 40h
0x180041e8a  jz      short loc_180041EB0
0x180041e8c  mov     rcx, [rcx+10h]
0x180041e90  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180041e97  xor     eax, eax
0x180041e99  mov     edx, 0Dh
0x180041e9e  cmp     dword ptr [rdi], 2
0x180041ea1  mov     r9, rbp
0x180041ea4  setz    al
0x180041ea7  mov     [rsp+48h+var_28], eax
0x180041eab  call    WPP_SF_Sd
0x180041eb0  mov     rbx, [rsp+48h+arg_8]
0x180041eb5  xor     eax, eax
0x180041eb7  add     rsp, 30h
0x180041ebb  pop     rdi
0x180041ebc  pop     rsi
0x180041ebd  pop     rbp
0x180041ebe  retn
```
