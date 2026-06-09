# CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)

- ea: `0x180049138`
- end: `0x180049261`
- name: `?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z`
- size: `297`
- prototype: `__int64 __usercall@<rax>(CMsftTrackInformation *__hidden this@<rcx>, struct IDiscRecorder2Ex *@<rdx>, unsigned int@<r8d>, enum _IMAPI_READ_TRACK_ADDRESS_TYPE@<r9d>, unsigned __int8)`
- caller_count: `9`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017b20`
- `0x180019a00`
- `0x18001a4f4`
- `0x18001b104`
- `0x18001cdf4`
- `0x18001d420`
- `0x180037f84`
- `0x180039a4c`
- `0x18003a554`

## callees

- `0x1800140f4`
- `0x18004908c`
- `0x180049138`
- `0x180049268`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004924e`
- `ole32!CoTaskMemFree` at `0x18004924e`

## pseudocode

```c
__int64 __fastcall CMsftTrackInformation::Init(
        CMsftTrackInformation *this,
        struct IDiscRecorder2Ex *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 a5)
{
  int inited; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v10; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-10h] BYREF

  pv[0] = 0;
  v10 = 0;
  inited = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, _QWORD, _QWORD, LPVOID *, int *))a2->lpVtbl->GetTrackInformation)(
             a2,
             a3,
             a4,
             pv,
             &v10);
  if ( inited >= 0 )
  {
    inited = CMsftTrackInformation::ValidateInitData((unsigned __int8 *)pv[0], v10);
    if ( inited >= 0 )
    {
      inited = CMsftTrackInformation::Init(this, (unsigned __int8 *)pv[0], v10, a5);
      if ( inited < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v8 = 20;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v8 = 19;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v8 = 18;
LABEL_16:
      WPP_SF_d(v7[2], v8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids, (unsigned int)inited);
    }
  }
  CoTaskMemFree(pv[0]);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180049138  mov     [rsp+arg_0], rbx
0x18004913d  push    rdi
0x18004913e  sub     rsp, 40h
0x180049142  mov     r10d, r9d
0x180049145  mov     r11d, r8d
0x180049148  mov     rbx, rdx
0x18004914b  mov     rdi, rcx
0x18004914e  mov     [rsp+48h+pv], 0
0x180049157  mov     [rsp+48h+var_18], 0
0x18004915f  mov     rax, [rdx]
0x180049162  lea     rcx, [rsp+48h+var_18]
0x180049167  mov     [rsp+48h+var_28], rcx
0x18004916c  lea     r9, [rsp+48h+pv]
0x180049171  mov     r8d, r10d
0x180049174  mov     edx, r11d
0x180049177  mov     rcx, rbx
0x18004917a  mov     rax, [rax+58h]
0x18004917e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049183  mov     ebx, eax
0x180049185  test    eax, eax
0x180049187  jns     short loc_1800491BB
0x180049189  lea     rax, WPP_GLOBAL_Control
0x180049190  mov     rcx, cs:WPP_GLOBAL_Control
0x180049197  cmp     rcx, rax
0x18004919a  jz      loc_180049249
0x1800491a0  test    byte ptr [rcx+1Ch], 4
0x1800491a4  jz      loc_180049249
0x1800491aa  cmp     byte ptr [rcx+19h], 3
0x1800491ae  jb      loc_180049249
0x1800491b4  mov     edx, 12h
0x1800491b9  jmp     short loc_180049236
0x1800491bb  mov     edx, [rsp+48h+var_18]; int
0x1800491bf  mov     rcx, [rsp+48h+pv]; unsigned __int8 *
0x1800491c4  call    ?ValidateInitData@CMsftTrackInformation@@CAJPEAEJ@Z; CMsftTrackInformation::ValidateInitData(uchar *,long)
0x1800491c9  mov     ebx, eax
0x1800491cb  test    eax, eax
0x1800491cd  jns     short loc_1800491F5
0x1800491cf  lea     rax, WPP_GLOBAL_Control
0x1800491d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800491dd  cmp     rcx, rax
0x1800491e0  jz      short loc_180049249
0x1800491e2  test    byte ptr [rcx+1Ch], 4
0x1800491e6  jz      short loc_180049249
0x1800491e8  cmp     byte ptr [rcx+19h], 3
0x1800491ec  jb      short loc_180049249
0x1800491ee  mov     edx, 13h
0x1800491f3  jmp     short loc_180049236
0x1800491f5  mov     r9b, [rsp+48h+arg_20]; unsigned __int8
0x1800491fa  mov     r8d, [rsp+48h+var_18]; int
0x1800491ff  mov     rdx, [rsp+48h+pv]; unsigned __int8 *
0x180049204  mov     rcx, rdi; this
0x180049207  call    ?Init@CMsftTrackInformation@@AEAAJPEAEJE@Z; CMsftTrackInformation::Init(uchar *,long,uchar)
0x18004920c  mov     ebx, eax
0x18004920e  test    eax, eax
0x180049210  jns     short loc_180049249
0x180049212  lea     rax, WPP_GLOBAL_Control
0x180049219  mov     rcx, cs:WPP_GLOBAL_Control
0x180049220  cmp     rcx, rax
0x180049223  jz      short loc_180049249
0x180049225  test    byte ptr [rcx+1Ch], 4
0x180049229  jz      short loc_180049249
0x18004922b  cmp     byte ptr [rcx+19h], 3
0x18004922f  jb      short loc_180049249
0x180049231  mov     edx, 14h
0x180049236  mov     r9d, ebx
0x180049239  lea     r8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids
0x180049240  mov     rcx, [rcx+10h]
0x180049244  call    WPP_SF_d
0x180049249  mov     rcx, [rsp+48h+pv]; pv
0x18004924e  call    cs:__imp_CoTaskMemFree
0x180049254  mov     eax, ebx
0x180049256  mov     rbx, [rsp+48h+arg_0]
0x18004925b  add     rsp, 40h
0x18004925f  pop     rdi
0x180049260  retn
```
