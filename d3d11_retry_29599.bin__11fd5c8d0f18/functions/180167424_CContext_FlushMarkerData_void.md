# CContext::FlushMarkerData(void)

- ea: `0x180167424`
- end: `0x180167553`
- name: `?FlushMarkerData@CContext@@QEAAXXZ`
- size: `303`
- prototype: `void __fastcall(CContext *__hidden this)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050f0`
- `0x1800051c0`
- `0x180042e60`
- `0x180081150`
- `0x180115d10`
- `0x18014e100`
- `0x180160a78`
- `0x180165b70`
- `0x180166770`
- `0x180167350`
- `0x1801675f0`
- `0x1801681e0`
- `0x1801bada0`
- `0x1801bf0e0`

## callees

- `0x1800a9d20`
- `0x180167424`
- `0x18016755c`
- `0x1801675b4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18016747b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18016747b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18016752d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18016752d`

## pseudocode

```c
void __fastcall CContext::FlushMarkerData(CContext *this)
{
  SMarkerData *v1; // rbx
  __int64 v2; // rsi
  __int64 v4; // rdx
  __int64 v5; // rax
  unsigned __int8 v6; // [rsp+20h] [rbp-69h] BYREF
  int v7; // [rsp+24h] [rbp-65h] BYREF
  LARGE_INTEGER Frequency; // [rsp+28h] [rbp-61h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-59h] BYREF
  char *v10; // [rsp+40h] [rbp-49h]
  __int64 v11; // [rsp+48h] [rbp-41h]
  char *v12; // [rsp+50h] [rbp-39h]
  __int64 v13; // [rsp+58h] [rbp-31h]
  char *v14; // [rsp+60h] [rbp-29h]
  __int64 v15; // [rsp+68h] [rbp-21h]
  unsigned __int8 *v16; // [rsp+70h] [rbp-19h]
  __int64 v17; // [rsp+78h] [rbp-11h]
  __int64 v18; // [rsp+80h] [rbp-9h]
  int v19; // [rsp+88h] [rbp-1h]
  int v20; // [rsp+8Ch] [rbp+3h]
  int *v21; // [rsp+90h] [rbp+7h]
  __int64 v22; // [rsp+98h] [rbp+Fh]
  __int64 v23; // [rsp+A0h] [rbp+17h]
  int v24; // [rsp+A8h] [rbp+1Fh]
  int v25; // [rsp+ACh] [rbp+23h]

  v1 = (CContext *)((char *)this + 39304);
  v2 = *((_QWORD *)this + 4919);
  v7 = *((_DWORD *)this + 9840) - v2;
  if ( v7 )
  {
    std::reverse<std::reverse_iterator<unsigned long *>>(*((_QWORD *)this + 4921), *((_QWORD *)this + 4922));
    Frequency.QuadPart = 0;
    QueryPerformanceFrequency(&Frequency);
    v4 = *((_QWORD *)this + 4922);
    UserData.Ptr = (ULONGLONG)&Frequency;
    v18 = v4;
    *(_QWORD *)&UserData.Size = 8;
    v10 = (char *)v1 + 24;
    v12 = (char *)this + 168;
    v14 = (char *)v1 + 16;
    v5 = *((_QWORD *)this + 4921) - v4;
    v11 = 8;
    v16 = &v6;
    v6 = v5 >> 2;
    v21 = &v7;
    v19 = 4 * v6;
    v24 = v7;
    v13 = 8;
    v15 = 4;
    v17 = 1;
    v20 = 0;
    v22 = 4;
    v23 = v2;
    v25 = 0;
    EventWrite(Direct3D11EtwProviderGuid_Context, &EventD3D11RuntimeMarkerData, 8u, &UserData);
  }
  SMarkerData::clear(v1);
}

```

## disassembly

```asm
0x180167424  push    rbp
0x180167426  push    rbx
0x180167427  push    rsi
0x180167428  push    rdi
0x180167429  lea     rbp, [rsp-3Fh]
0x18016742e  sub     rsp, 0C8h
0x180167435  mov     rax, cs:__security_cookie
0x18016743c  xor     rax, rsp
0x18016743f  mov     [rbp+57h+var_30], rax
0x180167443  mov     eax, [rcx+99C0h]
0x180167449  lea     rbx, [rcx+9988h]
0x180167450  mov     rsi, [rbx+30h]
0x180167454  mov     rdi, rcx
0x180167457  sub     eax, esi
0x180167459  mov     [rbp+57h+var_BC], eax
0x18016745c  jz      loc_180167533
0x180167462  mov     rdx, [rbx+48h]
0x180167466  mov     rcx, [rbx+40h]
0x18016746a  call    ??$reverse@V?$reverse_iterator@PEAK@std@@@std@@YAXV?$reverse_iterator@PEAK@0@0@Z; std::reverse<std::reverse_iterator<ulong *>>(std::reverse_iterator<ulong *>,std::reverse_iterator<ulong *>)
0x18016746f  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x180167473  mov     qword ptr [rbp+57h+Frequency], 0
0x18016747b  call    cs:__imp_QueryPerformanceFrequency
0x180167481  mov     rdx, [rdi+99D0h]
0x180167488  lea     rax, [rbp+57h+Frequency]
0x18016748c  mov     [rbp+57h+UserData.Ptr], rax
0x180167490  lea     r9, [rbp+57h+UserData]; UserData
0x180167494  mov     r8d, 8; UserDataCount
0x18016749a  mov     [rbp+57h+var_60], rdx
0x18016749e  lea     rax, [rbx+18h]
0x1801674a2  mov     qword ptr [rbp+57h+UserData.Size], r8
0x1801674a6  mov     [rbp+57h+var_A0], rax
0x1801674aa  lea     rax, [rdi+0A8h]
0x1801674b1  mov     [rbp+57h+var_90], rax
0x1801674b5  lea     rax, [rbx+10h]
0x1801674b9  mov     [rbp+57h+var_80], rax
0x1801674bd  mov     rax, [rdi+99C8h]
0x1801674c4  sub     rax, rdx
0x1801674c7  mov     [rbp+57h+var_98], r8
0x1801674cb  sar     rax, 2
0x1801674cf  lea     rdx, EventD3D11RuntimeMarkerData; EventDescriptor
0x1801674d6  movzx   ecx, al
0x1801674d9  lea     rax, [rbp+57h+var_C0]
0x1801674dd  mov     [rbp+57h+var_70], rax
0x1801674e1  lea     rax, [rbp+57h+var_BC]
0x1801674e5  mov     [rbp+57h+var_C0], cl
0x1801674e8  shl     ecx, 2
0x1801674eb  mov     [rbp+57h+var_50], rax
0x1801674ef  mov     eax, [rbp+57h+var_BC]
0x1801674f2  mov     [rbp+57h+var_58], ecx
0x1801674f5  mov     rcx, cs:Direct3D11EtwProviderGuid_Context; RegHandle
0x1801674fc  mov     [rbp+57h+var_38], eax
0x1801674ff  mov     [rbp+57h+var_88], r8
0x180167503  mov     [rbp+57h+var_78], 4
0x18016750b  mov     [rbp+57h+var_68], 1
0x180167513  mov     [rbp+57h+var_54], 0
0x18016751a  mov     [rbp+57h+var_48], 4
0x180167522  mov     [rbp+57h+var_40], rsi
0x180167526  mov     [rbp+57h+var_34], 0
0x18016752d  call    cs:__imp_EventWrite
0x180167533  mov     rcx, rbx; this
0x180167536  call    ?clear@SMarkerData@@QEAAXXZ; SMarkerData::clear(void)
0x18016753b  mov     rcx, [rbp+57h+var_30]
0x18016753f  xor     rcx, rsp; StackCookie
0x180167542  call    __security_check_cookie
0x180167547  add     rsp, 0C8h
0x18016754e  pop     rdi
0x18016754f  pop     rsi
0x180167550  pop     rbx
0x180167551  pop     rbp
0x180167552  retn
```
