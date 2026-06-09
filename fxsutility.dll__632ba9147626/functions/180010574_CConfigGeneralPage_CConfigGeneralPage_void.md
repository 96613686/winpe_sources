# CConfigGeneralPage::~CConfigGeneralPage(void)

- ea: `0x180010574`
- end: `0x1800105f8`
- name: `??1CConfigGeneralPage@@UEAA@XZ`
- size: `132`
- prototype: `void __fastcall(CConfigGeneralPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000fbd0`

## callees

- `0x180005eac`
- `0x180006318`
- `0x180010574`

## import_xrefs

- `FXSAPI!FaxFreeBuffer` at `0x1800105c7`
- `FXSAPI!FaxFreeBuffer` at `0x1800105c7`

## pseudocode

```c
void __fastcall CConfigGeneralPage::~CConfigGeneralPage(CConfigGeneralPage *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CConfigGeneralPage::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    FaxFreeBuffer(v2);
  pMemFree(*((LPVOID *)this + 7));
  pMemFree(*((LPVOID *)this + 13));
  pMemFree(*((LPVOID *)this + 14));
  *(_QWORD *)this = &CPage::`vftable';
}

```

## disassembly

```asm
0x180010574  push    rbx
0x180010576  sub     rsp, 20h
0x18001057a  lea     rax, ??_7CConfigGeneralPage@@6B@; const CConfigGeneralPage::`vftable'
0x180010581  mov     rbx, rcx
0x180010584  mov     [rcx], rax
0x180010587  mov     rcx, cs:WPP_GLOBAL_Control
0x18001058e  lea     rax, WPP_GLOBAL_Control
0x180010595  cmp     rcx, rax
0x180010598  jz      short loc_1800105BE
0x18001059a  test    dword ptr [rcx+1Ch], 100h
0x1800105a1  jz      short loc_1800105BE
0x1800105a3  cmp     byte ptr [rcx+19h], 5
0x1800105a7  jb      short loc_1800105BE
0x1800105a9  mov     rcx, [rcx+10h]
0x1800105ad  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800105b4  mov     edx, 0Ah
0x1800105b9  call    WPP_SF_
0x1800105be  mov     rcx, [rbx+20h]; Buffer
0x1800105c2  test    rcx, rcx
0x1800105c5  jz      short loc_1800105CD
0x1800105c7  call    cs:__imp_FaxFreeBuffer
0x1800105cd  mov     rcx, [rbx+38h]; lpMem
0x1800105d1  call    pMemFree
0x1800105d6  mov     rcx, [rbx+68h]; lpMem
0x1800105da  call    pMemFree
0x1800105df  mov     rcx, [rbx+70h]; lpMem
0x1800105e3  call    pMemFree
0x1800105e8  lea     rax, ??_7CPage@@6B@; const CPage::`vftable'
0x1800105ef  mov     [rbx], rax
0x1800105f2  add     rsp, 20h
0x1800105f6  pop     rbx
0x1800105f7  retn
```
