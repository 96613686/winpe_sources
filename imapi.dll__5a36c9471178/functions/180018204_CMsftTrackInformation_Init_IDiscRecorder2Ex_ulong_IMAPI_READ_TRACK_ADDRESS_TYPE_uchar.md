# CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)

- ea: `0x180018204`
- end: `0x180018347`
- name: `?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z`
- size: `323`
- prototype: `__int64 __usercall@<rax>(CMsftTrackInformation *__hidden this@<rcx>, struct IDiscRecorder2Ex *@<rdx>, unsigned int@<r8d>, enum _IMAPI_READ_TRACK_ADDRESS_TYPE@<r9d>, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800134e8`

## callees

- `0x180007bd4`
- `0x180018150`
- `0x180018204`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180018334`
- `ole32!CoTaskMemFree` at `0x180018334`

## pseudocode

```c
__int64 __fastcall CMsftTrackInformation::Init(
        CMsftTrackInformation *this,
        struct IDiscRecorder2Ex *a2,
        unsigned int a3,
        enum _IMAPI_READ_TRACK_ADDRESS_TYPE a4,
        int a5)
{
  int v6; // ebx
  unsigned __int8 v7; // r9
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  void *v10; // rdx
  __int64 v11; // r9
  LPVOID pv[3]; // [rsp+30h] [rbp-18h] BYREF

  pv[0] = 0;
  a5 = 0;
  v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, _QWORD, __int64, LPVOID *, int *))a2->lpVtbl->GetTrackInformation)(
         a2,
         a3,
         1,
         pv,
         &a5);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_21;
    }
    v9 = 18;
    goto LABEL_19;
  }
  v10 = pv[0];
  if ( pv[0]
    && a5 >= 2
    && (unsigned __int64)a5 >= 0x18
    && a5 == (*((unsigned __int8 *)pv[0] + 1) | (*(unsigned __int8 *)pv[0] << 8)) + 2 )
  {
    v6 = CMsftTrackInformation::Init(this, (unsigned __int8 *)pv[0], a5, v7);
    if ( v6 >= 0 )
      goto LABEL_21;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_21;
    }
    v9 = 20;
LABEL_19:
    v11 = (unsigned int)v6;
    goto LABEL_20;
  }
  v6 = -1062599937;
  v11 = 3232367359LL;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v9 = 19;
LABEL_20:
    WPP_SF_d(v8[2], v9, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids, v11);
LABEL_21:
    v10 = pv[0];
  }
  CoTaskMemFree(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018204  mov     [rsp+arg_0], rbx
0x180018209  push    rdi
0x18001820a  sub     rsp, 40h
0x18001820e  mov     r10d, r8d
0x180018211  mov     r11, rdx
0x180018214  mov     rdi, rcx
0x180018217  mov     [rsp+48h+pv], 0
0x180018220  mov     [rsp+48h+arg_20], 0
0x180018228  mov     rax, [rdx]
0x18001822b  lea     rcx, [rsp+48h+arg_20]
0x180018230  mov     [rsp+48h+var_28], rcx
0x180018235  lea     r9, [rsp+48h+pv]
0x18001823a  mov     r8d, 1
0x180018240  mov     edx, r10d
0x180018243  mov     rcx, r11
0x180018246  mov     rax, [rax+58h]
0x18001824a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001824f  mov     ebx, eax
0x180018251  test    eax, eax
0x180018253  jns     short loc_18001828A
0x180018255  lea     rax, WPP_GLOBAL_Control
0x18001825c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018263  cmp     rcx, rax
0x180018266  jz      loc_18001832C
0x18001826c  test    byte ptr [rcx+1Ch], 4
0x180018270  jz      loc_18001832C
0x180018276  cmp     byte ptr [rcx+19h], 3
0x18001827a  jb      loc_18001832C
0x180018280  mov     edx, 12h
0x180018285  jmp     loc_180018319
0x18001828a  mov     rdx, [rsp+48h+pv]; unsigned __int8 *
0x18001828f  test    rdx, rdx
0x180018292  jz      short loc_1800182B9
0x180018294  movsxd  r8, [rsp+48h+arg_20]; int
0x180018299  cmp     r8d, 2
0x18001829d  jl      short loc_1800182B9
0x18001829f  cmp     r8, 18h
0x1800182a3  jb      short loc_1800182B9
0x1800182a5  movzx   ecx, byte ptr [rdx]
0x1800182a8  shl     ecx, 8
0x1800182ab  movzx   eax, byte ptr [rdx+1]
0x1800182af  or      ecx, eax
0x1800182b1  add     ecx, 2
0x1800182b4  cmp     r8d, ecx
0x1800182b7  jz      short loc_1800182E7
0x1800182b9  mov     ebx, 0C0AA02FFh
0x1800182be  mov     r9d, ebx
0x1800182c1  lea     rax, WPP_GLOBAL_Control
0x1800182c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182cf  cmp     rcx, rax
0x1800182d2  jz      short loc_180018331
0x1800182d4  test    byte ptr [rcx+1Ch], 4
0x1800182d8  jz      short loc_180018331
0x1800182da  cmp     byte ptr [rcx+19h], 3
0x1800182de  jb      short loc_180018331
0x1800182e0  mov     edx, 13h
0x1800182e5  jmp     short loc_18001831C
0x1800182e7  mov     rcx, rdi; this
0x1800182ea  call    ?Init@CMsftTrackInformation@@AEAAJPEAEJE@Z; CMsftTrackInformation::Init(uchar *,long,uchar)
0x1800182ef  mov     ebx, eax
0x1800182f1  test    eax, eax
0x1800182f3  jns     short loc_18001832C
0x1800182f5  lea     rax, WPP_GLOBAL_Control
0x1800182fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018303  cmp     rcx, rax
0x180018306  jz      short loc_18001832C
0x180018308  test    byte ptr [rcx+1Ch], 4
0x18001830c  jz      short loc_18001832C
0x18001830e  cmp     byte ptr [rcx+19h], 3
0x180018312  jb      short loc_18001832C
0x180018314  mov     edx, 14h
0x180018319  mov     r9d, ebx
0x18001831c  lea     r8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids
0x180018323  mov     rcx, [rcx+10h]
0x180018327  call    WPP_SF_d
0x18001832c  mov     rdx, [rsp+48h+pv]
0x180018331  mov     rcx, rdx; pv
0x180018334  call    cs:__imp_CoTaskMemFree
0x18001833a  mov     eax, ebx
0x18001833c  mov     rbx, [rsp+48h+arg_0]
0x180018341  add     rsp, 40h
0x180018345  pop     rdi
0x180018346  retn
```
