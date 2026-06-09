# RxOrphanFobx

- ea: `0x14006aa40`
- end: `0x14006ab72`
- name: `RxOrphanFobx`
- size: `306`
- prototype: `__int64 __fastcall(PFOBX Fobx)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14005b620`
- `0x14006a840`

## callees

- `0x140004180`
- `0x140008030`
- `0x140008190`
- `0x14000d1e0`
- `0x14000e9f0`
- `0x140014d10`
- `0x140057a80`
- `0x14006aa40`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x14006ab61`
- `ntoskrnl!IoRemoveShareAccess` at `0x14006ab61`

## pseudocode

```c
__int64 __fastcall RxOrphanFobx(PFOBX Fobx)
{
  __int64 result; // rax
  _QWORD *Context2; // rsi
  ULONG_PTR v4; // rdi
  __int64 v5; // r8
  struct _FILE_OBJECT *PipeHandleInformation; // rcx
  signed int FobxSerialNumber; // eax

  result = Fobx->FobxSerialNumber;
  if ( (result & 2) == 0 )
  {
    Context2 = Fobx->Context2;
    v4 = Context2[4];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        78,
        (unsigned int)WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
        (_DWORD)Fobx,
        Context2[10]);
    }
    RxCloseFileObjectForTurboIo(Fobx->PipeHandleInformation, v4);
    if ( !BYTE2(Fobx->Specific.DiskFile.PredictedReadOffset) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&Fobx->1 + 5) + 192LL));
      BYTE2(Fobx->Specific.DiskFile.PredictedReadOffset) = 1;
    }
    RxSelectAndSwitchPagingFileObject(v4, 0, (ULONG_PTR)Fobx, 0);
    LOBYTE(v5) = 1;
    RxAcquirePagingIoResource(0, v4, v5);
    if ( (Fobx->FobxSerialNumber & 0x400000) == 0 )
    {
      RxCleanupFobxForMiniRdr(0);
      PipeHandleInformation = (struct _FILE_OBJECT *)Fobx->PipeHandleInformation;
      if ( PipeHandleInformation )
      {
        if ( !*(_BYTE *)(*(_QWORD *)(v4 + 120) + 77LL) )
        {
          FobxSerialNumber = Fobx->FobxSerialNumber;
          if ( (FobxSerialNumber & 0x40000000) == 0 && FobxSerialNumber >= 0 )
            IoRemoveShareAccess(PipeHandleInformation, (PSHARE_ACCESS)(v4 + 424));
        }
      }
    }
    RxCloseAssociatedSrvOpen(0, Fobx);
    Fobx->FobxSerialNumber |= 2u;
    return RxReleasePagingIoResource(0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x14006aa40  push    rbx
0x14006aa42  sub     rsp, 30h
0x14006aa46  mov     eax, [rcx+48h]
0x14006aa49  mov     rbx, rcx
0x14006aa4c  test    al, 2
0x14006aa4e  jnz     loc_14006AAEF
0x14006aa54  mov     [rsp+38h+arg_0], rsi
0x14006aa59  mov     rsi, [rcx+20h]
0x14006aa5d  mov     [rsp+38h+arg_8], rdi
0x14006aa62  mov     rdi, [rsi+20h]
0x14006aa66  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aa6d  lea     rax, WPP_GLOBAL_Control
0x14006aa74  cmp     rcx, rax
0x14006aa77  jz      short loc_14006AA80
0x14006aa79  mov     eax, [rcx+2Ch]
0x14006aa7c  test    al, 1
0x14006aa7e  jnz     short loc_14006AAF6
0x14006aa80  mov     rcx, [rbx+30h]
0x14006aa84  mov     rdx, rdi
0x14006aa87  call    RxCloseFileObjectForTurboIo
0x14006aa8c  cmp     byte ptr [rbx+92h], 0
0x14006aa93  jnz     short loc_14006AAA7
0x14006aa95  mov     rax, [rbx+28h]
0x14006aa99  lock dec dword ptr [rax+0C0h]
0x14006aaa0  mov     byte ptr [rbx+92h], 1
0x14006aaa7  xor     r9d, r9d
0x14006aaaa  mov     r8, rbx
0x14006aaad  xor     edx, edx
0x14006aaaf  mov     rcx, rdi; BugCheckParameter3
0x14006aab2  call    RxSelectAndSwitchPagingFileObject
0x14006aab7  mov     r8b, 1
0x14006aaba  mov     rdx, rdi
0x14006aabd  xor     ecx, ecx
0x14006aabf  call    RxAcquirePagingIoResource
0x14006aac4  test    dword ptr [rbx+48h], 400000h
0x14006aacb  jz      short loc_14006AB22
0x14006aacd  mov     rdx, rbx; Fobx
0x14006aad0  xor     ecx, ecx; RxContext
0x14006aad2  call    RxCloseAssociatedSrvOpen
0x14006aad7  or      dword ptr [rbx+48h], 2
0x14006aadb  mov     rdx, rdi
0x14006aade  xor     ecx, ecx
0x14006aae0  call    RxReleasePagingIoResource
0x14006aae5  mov     rdi, [rsp+38h+arg_8]
0x14006aaea  mov     rsi, [rsp+38h+arg_0]
0x14006aaef  add     rsp, 30h
0x14006aaf3  pop     rbx
0x14006aaf4  retn
0x14006aaf6  cmp     byte ptr [rcx+29h], 1
0x14006aafa  jb      short loc_14006AA80
0x14006aafc  mov     rax, [rsi+50h]
0x14006ab00  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14006ab07  mov     rcx, [rcx+18h]
0x14006ab0b  mov     edx, 4Eh ; 'N'
0x14006ab10  mov     r9, rbx
0x14006ab13  mov     [rsp+38h+var_18], rax
0x14006ab18  call    WPP_SF_qZ
0x14006ab1d  jmp     loc_14006AA80
0x14006ab22  mov     r9, rbx
0x14006ab25  mov     r8, rsi
0x14006ab28  mov     rdx, rdi
0x14006ab2b  xor     ecx, ecx; RxContext
0x14006ab2d  call    RxCleanupFobxForMiniRdr
0x14006ab32  mov     rcx, [rbx+30h]; FileObject
0x14006ab36  test    rcx, rcx
0x14006ab39  jz      short loc_14006AACD
0x14006ab3b  mov     rax, [rdi+78h]
0x14006ab3f  cmp     byte ptr [rax+4Dh], 0
0x14006ab43  jnz     short loc_14006AACD
0x14006ab45  mov     eax, [rbx+48h]
0x14006ab48  bt      eax, 1Eh
0x14006ab4c  jb      loc_14006AACD
0x14006ab52  test    eax, eax
0x14006ab54  js      loc_14006AACD
0x14006ab5a  lea     rdx, [rdi+1A8h]; ShareAccess
0x14006ab61  call    cs:__imp_IoRemoveShareAccess
0x14006ab68  nop     dword ptr [rax+rax+00h]
0x14006ab6d  jmp     loc_14006AACD
```
