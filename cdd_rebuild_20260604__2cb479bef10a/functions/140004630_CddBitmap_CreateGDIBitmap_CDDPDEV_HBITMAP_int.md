# CddBitmap::CreateGDIBitmap(CDDPDEV *,HBITMAP__ * *,int)

- ea: `0x140004630`
- end: `0x1400048b5`
- name: `?CreateGDIBitmap@CddBitmap@@QEAAJPEAUCDDPDEV@@PEAPEAUHBITMAP__@@H@Z`
- size: `645`
- prototype: `__int64 __fastcall(DHSURF dhsurf, struct CDDPDEV *, HBITMAP *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003840`
- `0x14001fcb0`
- `0x1400319f0`

## callees

- `0x140004630`
- `0x140020c58`
- `0x14002a1b0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdError` at `0x1400046f8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000481b`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400046f8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000481b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140004764`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140004764`
- `watchdog!WdLogSingleEntry0` at `0x1400046e1`
- `watchdog!WdLogSingleEntry0` at `0x14000474e`
- `watchdog!WdLogSingleEntry0` at `0x140004802`
- `watchdog!WdLogSingleEntry0` at `0x1400046e1`
- `watchdog!WdLogSingleEntry0` at `0x14000474e`
- `watchdog!WdLogSingleEntry0` at `0x140004802`
- `WIN32K!EngCreateDeviceBitmap` at `0x1400046c5`
- `WIN32K!EngCreateDeviceBitmap` at `0x1400046c5`
- `WIN32K!EngCreateRedirectionDeviceBitmap` at `0x1400046b7`
- `WIN32K!EngCreateRedirectionDeviceBitmap` at `0x1400046b7`
- `WIN32K!EngModifySurface` at `0x1400047c9`
- `WIN32K!EngModifySurface` at `0x1400047c9`
- `WIN32K!EngDeleteSurface` at `0x140004853`
- `WIN32K!EngDeleteSemaphore` at `0x14000487b`
- `WIN32K!EngDeleteSemaphore` at `0x14000487b`
- `WIN32K!EngCreateSemaphore` at `0x14000467c`
- `WIN32K!EngCreateSemaphore` at `0x14000467c`

## pseudocode

```c
__int64 __fastcall CddBitmap::CreateGDIBitmap(DHSURF dhsurf, HDEV *a2, HSURF *a3, int a4)
{
  bool v8; // zf
  HSEMAPHORE Semaphore; // rax
  ULONG v10; // r8d
  HBITMAP RedirectionDeviceBitmap; // rax
  HSURF v12; // rdi
  _QWORD *v13; // rax
  FLONG v14; // r9d
  _QWORD *v15; // rax
  _QWORD *v17; // rax
  HSEMAPHORE v18; // rcx
  BOOL (__stdcall *v19[2])(HSURF); // [rsp+40h] [rbp-28h] BYREF
  SIZEL sizl; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_DWORD *)dhsurf + 4) > 0x7FFFFFFFu )
    return 3221225485LL;
  LODWORD(sizl.cx) = dhsurf[4];
  if ( *((_DWORD *)dhsurf + 5) > 0x7FFFFFFFu )
    return 3221225485LL;
  v8 = *((_QWORD *)dhsurf + 24) == 0;
  sizl.cy = (int)dhsurf[5];
  if ( !v8
    || (Semaphore = EngCreateSemaphore(), *((_QWORD *)dhsurf + 24) = Semaphore, *((_DWORD *)dhsurf + 50) = 0, Semaphore) )
  {
    v10 = *((_DWORD *)dhsurf + 7);
    if ( ((_DWORD)dhsurf[32] & 2) != 0 )
      RedirectionDeviceBitmap = EngCreateRedirectionDeviceBitmap(0, sizl, v10);
    else
      RedirectionDeviceBitmap = EngCreateDeviceBitmap(0, sizl, v10);
    sizl = (SIZEL)RedirectionDeviceBitmap;
    v12 = (HSURF)RedirectionDeviceBitmap;
    if ( RedirectionDeviceBitmap )
    {
      v14 = 7;
      if ( a4 )
      {
        if ( ((_DWORD)dhsurf[32] & 2) == 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1496;
          v15 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v15[3] = gCddImageInfo;
          v15[4] = (unsigned int)dword_14003E570;
          v15[5] = 215857758;
          WdLogGlobalForLineNumber = 1496;
        }
        v14 = 15;
      }
      if ( EngModifySurface(v12, a2[1], 0x3B5EFu, v14, dhsurf, 0, 0, 0)
        && ((unsigned int (__fastcall *)(HSURF, HDEV))a2[84])(v12, a2[308]) )
      {
        *a3 = v12;
        return 0;
      }
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1516;
      v17 = (_QWORD *)WdLogNewEntry5_WdError();
      sizl = (SIZEL)v12;
      v17[3] = gCddImageInfo;
      v17[4] = (unsigned int)dword_14003E570;
      v17[5] = 215857758;
      v19[0] = EngDeleteSurface;
      WdLogGlobalForLineNumber = 1516;
      wistd::invoke<void (*)(void *),_D3DKMT_DISPLAYMODE * &>(v19, &sizl);
    }
    else
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1470;
      v13 = (_QWORD *)WdLogNewEntry5_WdError();
      v13[3] = gCddImageInfo;
      v13[4] = (unsigned int)dword_14003E570;
      v13[5] = 215857758;
      WdLogGlobalForLineNumber = 1470;
      wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(&sizl);
    }
    v18 = (HSEMAPHORE)*((_QWORD *)dhsurf + 24);
    if ( v18 )
    {
      if ( !a4 )
      {
        EngDeleteSemaphore(v18);
        *((_QWORD *)dhsurf + 24) = 0;
      }
    }
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140004630  mov     [rsp+arg_8], rbx
0x140004635  mov     [rsp+arg_10], rsi
0x14000463a  push    rdi
0x14000463b  push    r14
0x14000463d  push    r15
0x14000463f  sub     rsp, 50h
0x140004643  mov     eax, [rcx+10h]
0x140004646  mov     rbx, rcx
0x140004649  mov     ecx, 7FFFFFFFh
0x14000464e  mov     esi, r9d
0x140004651  mov     r14, r8
0x140004654  mov     r15, rdx
0x140004657  cmp     eax, ecx
0x140004659  ja      loc_140004899
0x14000465f  mov     [rsp+68h+sizl.cx], eax
0x140004663  mov     eax, [rbx+14h]
0x140004666  cmp     eax, ecx
0x140004668  ja      loc_140004899
0x14000466e  cmp     qword ptr [rbx+0C0h], 0
0x140004676  mov     [rsp+68h+sizl.cy], eax
0x14000467a  jnz     short loc_1400046A2
0x14000467c  call    cs:__imp_EngCreateSemaphore
0x140004683  nop     dword ptr [rax+rax+00h]
0x140004688  mov     [rbx+0C0h], rax
0x14000468f  mov     dword ptr [rbx+0C8h], 0
0x140004699  test    rax, rax
0x14000469c  jz      loc_140004892
0x1400046a2  mov     eax, [rbx+80h]
0x1400046a8  xor     ecx, ecx; dhsurf
0x1400046aa  mov     r8d, [rbx+1Ch]; iFormatCompat
0x1400046ae  mov     rdx, qword ptr [rsp+68h+sizl.cx]; sizl
0x1400046b3  test    al, 2
0x1400046b5  jz      short loc_1400046C5
0x1400046b7  call    cs:__imp_EngCreateRedirectionDeviceBitmap
0x1400046be  nop     dword ptr [rax+rax+00h]
0x1400046c3  jmp     short loc_1400046D1
0x1400046c5  call    cs:__imp_EngCreateDeviceBitmap
0x1400046cc  nop     dword ptr [rax+rax+00h]
0x1400046d1  mov     qword ptr [rsp+68h+sizl.cx], rax
0x1400046d6  mov     rdi, rax
0x1400046d9  test    rax, rax
0x1400046dc  jnz     short loc_140004736
0x1400046de  lea     ecx, [rax+2]
0x1400046e1  call    cs:__imp_WdLogSingleEntry0
0x1400046e8  nop     dword ptr [rax+rax+00h]
0x1400046ed  mov     edi, 5BEh
0x1400046f2  mov     cs:WdLogGlobalForLineNumber, edi
0x1400046f8  call    cs:__imp_WdLogNewEntry5_WdError
0x1400046ff  nop     dword ptr [rax+rax+00h]
0x140004704  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000470b  mov     [rax+18h], rcx
0x14000470f  mov     ecx, cs:dword_14003E570
0x140004715  mov     [rax+20h], rcx
0x140004719  lea     rcx, [rsp+68h+sizl]
0x14000471e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140004726  mov     cs:WdLogGlobalForLineNumber, edi
0x14000472c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSURF__@@$$A6AHPEAU1@@Z$1?EngDeleteSurface@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(void)
0x140004731  jmp     loc_14000486B
0x140004736  mov     r9d, 7
0x14000473c  test    esi, esi
0x14000473e  jz      short loc_14000479D
0x140004740  mov     eax, [rbx+80h]
0x140004746  test    al, 2
0x140004748  jnz     short loc_140004797
0x14000474a  lea     ecx, [r9-6]
0x14000474e  call    cs:__imp_WdLogSingleEntry0
0x140004755  nop     dword ptr [rax+rax+00h]
0x14000475a  mov     cs:WdLogGlobalForLineNumber, 5D8h
0x140004764  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000476b  nop     dword ptr [rax+rax+00h]
0x140004770  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140004777  mov     [rax+18h], rcx
0x14000477b  mov     ecx, cs:dword_14003E570
0x140004781  mov     [rax+20h], rcx
0x140004785  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000478d  mov     cs:WdLogGlobalForLineNumber, 5D8h
0x140004797  mov     r9d, 0Fh; flSurface
0x14000479d  mov     rdx, [r15+8]; hdev
0x1400047a1  mov     r8d, 3B5EFh; flHooks
0x1400047a7  mov     [rsp+68h+pvReserved], 0; pvReserved
0x1400047b0  mov     rcx, rdi; hsurf
0x1400047b3  mov     [rsp+68h+lDelta], 0; lDelta
0x1400047bb  mov     [rsp+68h+pvScan0], 0; pvScan0
0x1400047c4  mov     [rsp+68h+dhsurf], rbx; dhsurf
0x1400047c9  call    cs:__imp_EngModifySurface
0x1400047d0  nop     dword ptr [rax+rax+00h]
0x1400047d5  test    eax, eax
0x1400047d7  jz      short loc_1400047FD
0x1400047d9  mov     rdx, [r15+9A0h]
0x1400047e0  mov     rcx, rdi
0x1400047e3  mov     rax, [r15+2A0h]
0x1400047ea  call    _guard_dispatch_icall
0x1400047ef  test    eax, eax
0x1400047f1  jz      short loc_1400047FD
0x1400047f3  mov     [r14], rdi
0x1400047f6  xor     eax, eax
0x1400047f8  jmp     loc_14000489E
0x1400047fd  mov     ecx, 2
0x140004802  call    cs:__imp_WdLogSingleEntry0
0x140004809  nop     dword ptr [rax+rax+00h]
0x14000480e  mov     r14d, 5ECh
0x140004814  mov     cs:WdLogGlobalForLineNumber, r14d
0x14000481b  call    cs:__imp_WdLogNewEntry5_WdError
0x140004822  nop     dword ptr [rax+rax+00h]
0x140004827  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000482e  lea     rdx, [rsp+68h+sizl]
0x140004833  mov     qword ptr [rsp+68h+sizl.cx], rdi
0x140004838  mov     [rax+18h], rcx
0x14000483c  mov     ecx, cs:dword_14003E570
0x140004842  mov     [rax+20h], rcx
0x140004846  lea     rcx, [rsp+68h+var_28]
0x14000484b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140004853  mov     rax, cs:__imp_EngDeleteSurface
0x14000485a  mov     [rsp+68h+var_28], rax
0x14000485f  mov     cs:WdLogGlobalForLineNumber, r14d
0x140004866  call    ??$invoke@P6AXPEAX@ZAEAPEAU_D3DKMT_DISPLAYMODE@@@wistd@@YAX$$QEAP6AXPEAX@ZAEAPEAU_D3DKMT_DISPLAYMODE@@@Z; wistd::invoke<void (*)(void *),_D3DKMT_DISPLAYMODE * &>(void (*&&)(void *),_D3DKMT_DISPLAYMODE * &)
0x14000486b  mov     rcx, [rbx+0C0h]; hsem
0x140004872  test    rcx, rcx
0x140004875  jz      short loc_140004892
0x140004877  test    esi, esi
0x140004879  jnz     short loc_140004892
0x14000487b  call    cs:__imp_EngDeleteSemaphore
0x140004882  nop     dword ptr [rax+rax+00h]
0x140004887  mov     qword ptr [rbx+0C0h], 0
0x140004892  mov     eax, 0C0000001h
0x140004897  jmp     short loc_14000489E
0x140004899  mov     eax, 0C000000Dh
0x14000489e  lea     r11, [rsp+68h+var_18]
0x1400048a3  mov     rbx, [r11+28h]
0x1400048a7  mov     rsi, [r11+30h]
0x1400048ab  mov     rsp, r11
0x1400048ae  pop     r15
0x1400048b0  pop     r14
0x1400048b2  pop     rdi
0x1400048b3  retn
```
