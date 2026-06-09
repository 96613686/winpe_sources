# CMSDiscMasterObj::InitializeOnce(void)

- ea: `0x18000c4a8`
- end: `0x18000c58f`
- name: `?InitializeOnce@CMSDiscMasterObj@@AEAAEXZ`
- size: `231`
- prototype: `unsigned __int8 __fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000ce60`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x18000c4a8`
- `0x1800107e8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000c4c8`
- `KERNEL32!CreateEventW` at `0x18000c4c8`
- `KERNEL32!GetLastError` at `0x18000c4fb`
- `KERNEL32!GetLastError` at `0x18000c4fb`

## pseudocode

```c
unsigned __int8 __fastcall CMSDiscMasterObj::InitializeOnce(CMSDiscMasterObj *this)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax

  EventW = (HANDLE)*((_QWORD *)this + 53);
  if ( !EventW )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 53) = EventW;
    if ( !EventW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids, LastError);
      }
      return 0;
    }
  }
  if ( !*((_BYTE *)this + 352) )
  {
    if ( CMyUpdateList::Init((CMSDiscMasterObj *)((char *)this + 192), EventW, (unsigned __int8 *)this + 420) )
      *((_BYTE *)this + 352) = 1;
    if ( !*((_BYTE *)this + 352) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000c4a8  push    rbx
0x18000c4aa  sub     rsp, 20h
0x18000c4ae  mov     rax, [rcx+1A8h]
0x18000c4b5  mov     rbx, rcx
0x18000c4b8  test    rax, rax
0x18000c4bb  jnz     short loc_18000C522
0x18000c4bd  xor     r9d, r9d; lpName
0x18000c4c0  lea     edx, [rax+1]; bManualReset
0x18000c4c3  xor     r8d, r8d; bInitialState
0x18000c4c6  xor     ecx, ecx; lpEventAttributes
0x18000c4c8  call    cs:__imp_CreateEventW
0x18000c4ce  mov     [rbx+1A8h], rax
0x18000c4d5  test    rax, rax
0x18000c4d8  jnz     short loc_18000C522
0x18000c4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4e1  lea     rax, WPP_GLOBAL_Control
0x18000c4e8  cmp     rcx, rax
0x18000c4eb  jz      loc_18000C583
0x18000c4f1  test    byte ptr [rcx+44h], 1
0x18000c4f5  jz      loc_18000C583
0x18000c4fb  call    cs:__imp_GetLastError
0x18000c501  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c508  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c50f  mov     edx, 0Bh
0x18000c514  mov     r9d, eax
0x18000c517  mov     rcx, [rcx+38h]
0x18000c51b  call    WPP_SF_d
0x18000c520  jmp     short loc_18000C583
0x18000c522  cmp     byte ptr [rbx+160h], 0
0x18000c529  jnz     short loc_18000C587
0x18000c52b  lea     r8, [rbx+1A4h]; unsigned __int8 *
0x18000c532  mov     rdx, rax; void *
0x18000c535  lea     rcx, [rbx+0C0h]; this
0x18000c53c  call    ?Init@CMyUpdateList@@QEAAEPEAXPEAE@Z; CMyUpdateList::Init(void *,uchar *)
0x18000c541  test    al, al
0x18000c543  jz      short loc_18000C54C
0x18000c545  mov     byte ptr [rbx+160h], 1
0x18000c54c  cmp     byte ptr [rbx+160h], 0
0x18000c553  jnz     short loc_18000C587
0x18000c555  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c55c  lea     rax, WPP_GLOBAL_Control
0x18000c563  cmp     rcx, rax
0x18000c566  jz      short loc_18000C583
0x18000c568  test    byte ptr [rcx+44h], 1
0x18000c56c  jz      short loc_18000C583
0x18000c56e  mov     rcx, [rcx+38h]
0x18000c572  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c579  mov     edx, 0Ch
0x18000c57e  call    WPP_SF_
0x18000c583  xor     al, al
0x18000c585  jmp     short loc_18000C589
0x18000c587  mov     al, 1
0x18000c589  add     rsp, 20h
0x18000c58d  pop     rbx
0x18000c58e  retn
```
