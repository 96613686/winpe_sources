# EventWriteOpenFile

- ea: `0x140004fb0`
- end: `0x14000522e`
- name: `EventWriteOpenFile`
- size: `638`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, char, char, char, char, char, char, wchar_t *, int, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400275b4`

## callees

- `0x140004fb0`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140005206`
- `ntoskrnl!EtwWrite` at `0x140005206`
- `ntoskrnl!RtlLengthSid` at `0x14000503d`
- `ntoskrnl!RtlLengthSid` at `0x14000503d`

## pseudocode

```c
__int64 __fastcall EventWriteOpenFile(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        wchar_t *Str,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        wchar_t *a16,
        int a17,
        __int64 a18,
        char a19)
{
  PSID v19; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v23; // eax
  const wchar_t *v24; // rsi
  int v25; // ebx
  int v26; // ecx
  const WCHAR *v27; // r14
  const WCHAR *v28; // rax
  const wchar_t *v29; // rsi
  bool v30; // zf
  int v31; // eax
  __int64 v32; // rax
  int v33; // ecx
  unsigned int v34; // ebx
  __int64 v35; // [rsp+70h] [rbp+40h] BYREF
  int v36; // [rsp+78h] [rbp+48h] BYREF
  __int64 v37; // [rsp+80h] [rbp+50h] BYREF
  int v38; // [rsp+88h] [rbp+58h] BYREF

  v38 = a4;
  v37 = a3;
  v36 = a2;
  v35 = a1;
  v19 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(19);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v35;
  EtwDescriptorBuffer[2] = &v36;
  EtwDescriptorBuffer[4] = &v37;
  EtwDescriptorBuffer[6] = &v38;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v19 )
    v23 = RtlLengthSid(v19);
  else
    v23 = 0;
  v24 = Str;
  *((_DWORD *)UserData + 18) = v23;
  UserData[8] = v19;
  v25 = 2;
  UserData[10] = &a6;
  *((_DWORD *)UserData + 19) = 0;
  UserData[11] = 4;
  if ( v24 )
    v26 = 2 * wcslen_0(v24) + 2;
  else
    v26 = 2;
  *((_DWORD *)UserData + 26) = v26;
  v27 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v28 = &SourceString;
  UserData[15] = 4;
  if ( v24 )
    v28 = v24;
  UserData[17] = 4;
  v29 = a16;
  UserData[12] = v28;
  UserData[14] = &a8;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[20] = &a11;
  UserData[22] = &a12;
  UserData[24] = &a13;
  UserData[26] = &a14;
  UserData[28] = &a15;
  UserData[19] = 4;
  UserData[21] = 8;
  UserData[23] = 4;
  UserData[25] = 4;
  UserData[27] = 2;
  UserData[29] = 1;
  v30 = v29 == 0;
  if ( v29 )
  {
    v31 = wcslen_0(v29);
    v30 = v29 == 0;
    v25 = 2 * v31 + 2;
  }
  if ( !v30 )
    v27 = v29;
  *((_DWORD *)UserData + 62) = v25;
  UserData[30] = v27;
  UserData[32] = &a17;
  v32 = a18;
  *((_DWORD *)UserData + 63) = 0;
  UserData[33] = 4;
  v33 = a17;
  UserData[34] = v32;
  UserData[36] = &a19;
  *((_DWORD *)UserData + 70) = v33;
  *((_DWORD *)UserData + 71) = 0;
  UserData[37] = 1;
  v34 = EtwWrite(Microsoft_Windows_SECHandle, &Event42, 0, 0x13u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v34;
}

```

## disassembly

```asm
0x140004fb0  mov     rax, rsp
0x140004fb3  mov     [rax+20h], r9d
0x140004fb7  mov     [rax+18h], r8
0x140004fbb  mov     [rax+10h], edx
0x140004fbe  mov     [rax+8], rcx
0x140004fc2  push    rbp
0x140004fc3  push    rbx
0x140004fc4  push    rsi
0x140004fc5  push    rdi
0x140004fc6  push    r12
0x140004fc8  push    r14
0x140004fca  push    r15
0x140004fcc  mov     rbp, rsp
0x140004fcf  sub     rsp, 30h
0x140004fd3  mov     rbx, [rbp+Sid]
0x140004fd7  mov     ecx, 13h
0x140004fdc  call    SecGetEtwDescriptorBuffer
0x140004fe1  xor     r15d, r15d
0x140004fe4  mov     rdi, rax
0x140004fe7  test    rax, rax
0x140004fea  jnz     short loc_140004FF6
0x140004fec  mov     eax, 0C000009Ah
0x140004ff1  jmp     loc_14000521E
0x140004ff6  mov     qword ptr [rdi+8], 8
0x140004ffe  lea     rax, [rbp+arg_0]
0x140005002  mov     [rdi], rax
0x140005005  lea     rax, [rbp+arg_8]
0x140005009  mov     [rdi+10h], rax
0x14000500d  lea     rax, [rbp+arg_10]
0x140005011  mov     [rdi+20h], rax
0x140005015  lea     rax, [rbp+arg_18]
0x140005019  mov     [rdi+30h], rax
0x14000501d  mov     qword ptr [rdi+18h], 4
0x140005025  mov     qword ptr [rdi+28h], 8
0x14000502d  mov     qword ptr [rdi+38h], 4
0x140005035  test    rbx, rbx
0x140005038  jz      short loc_14000504B
0x14000503a  mov     rcx, rbx; Sid
0x14000503d  call    cs:__imp_RtlLengthSid
0x140005044  nop     dword ptr [rax+rax+00h]
0x140005049  jmp     short loc_14000504E
0x14000504b  mov     eax, r15d
0x14000504e  mov     rsi, [rbp+Str]
0x140005052  mov     [rdi+48h], eax
0x140005055  lea     rax, [rbp+arg_28]
0x140005059  mov     [rdi+40h], rbx
0x14000505d  mov     ebx, 2
0x140005062  mov     [rdi+50h], rax
0x140005066  mov     [rdi+4Ch], r15d
0x14000506a  mov     qword ptr [rdi+58h], 4
0x140005072  test    rsi, rsi
0x140005075  jz      short loc_140005088
0x140005077  mov     rcx, rsi; Str
0x14000507a  call    wcslen_0
0x14000507f  lea     ecx, ds:2[rax*2]
0x140005086  jmp     short loc_14000508A
0x140005088  mov     ecx, ebx
0x14000508a  test    rsi, rsi
0x14000508d  mov     [rdi+68h], ecx
0x140005090  lea     r14, SourceString
0x140005097  mov     [rdi+6Ch], r15d
0x14000509b  mov     rax, r14
0x14000509e  mov     qword ptr [rdi+78h], 4
0x1400050a6  cmovnz  rax, rsi
0x1400050aa  mov     qword ptr [rdi+88h], 4
0x1400050b5  mov     rsi, [rbp+arg_78]
0x1400050bc  mov     [rdi+60h], rax
0x1400050c0  lea     rax, [rbp+arg_38]
0x1400050c4  mov     [rdi+70h], rax
0x1400050c8  lea     rax, [rbp+arg_40]
0x1400050cf  mov     [rdi+80h], rax
0x1400050d6  lea     rax, [rbp+arg_48]
0x1400050dd  mov     [rdi+90h], rax
0x1400050e4  lea     rax, [rbp+arg_50]
0x1400050eb  mov     [rdi+0A0h], rax
0x1400050f2  lea     rax, [rbp+arg_58]
0x1400050f9  mov     [rdi+0B0h], rax
0x140005100  lea     rax, [rbp+arg_60]
0x140005107  mov     [rdi+0C0h], rax
0x14000510e  lea     rax, [rbp+arg_68]
0x140005115  mov     [rdi+0D0h], rax
0x14000511c  lea     rax, [rbp+arg_70]
0x140005123  mov     [rdi+0E0h], rax
0x14000512a  mov     qword ptr [rdi+98h], 4
0x140005135  mov     qword ptr [rdi+0A8h], 8
0x140005140  mov     qword ptr [rdi+0B8h], 4
0x14000514b  mov     qword ptr [rdi+0C8h], 4
0x140005156  mov     [rdi+0D8h], rbx
0x14000515d  mov     qword ptr [rdi+0E8h], 1
0x140005168  test    rsi, rsi
0x14000516b  jz      short loc_14000517F
0x14000516d  mov     rcx, rsi; Str
0x140005170  call    wcslen_0
0x140005175  test    rsi, rsi
0x140005178  lea     ebx, ds:2[rax*2]
0x14000517f  cmovnz  r14, rsi
0x140005183  mov     [rdi+0F8h], ebx
0x140005189  mov     [rdi+0F0h], r14
0x140005190  lea     rax, [rbp+arg_80]
0x140005197  mov     [rdi+100h], rax
0x14000519e  lea     rdx, Event42; EventDescriptor
0x1400051a5  mov     rax, [rbp+arg_88]
0x1400051ac  mov     r9d, 13h; UserDataCount
0x1400051b2  mov     [rdi+0FCh], r15d
0x1400051b9  xor     r8d, r8d; ActivityId
0x1400051bc  mov     qword ptr [rdi+108h], 4
0x1400051c7  mov     ecx, [rbp+arg_80]
0x1400051cd  mov     [rdi+110h], rax
0x1400051d4  lea     rax, [rbp+arg_90]
0x1400051db  mov     [rdi+120h], rax
0x1400051e2  mov     [rdi+118h], ecx
0x1400051e8  mov     [rdi+11Ch], r15d
0x1400051ef  mov     qword ptr [rdi+128h], 1
0x1400051fa  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140005201  mov     [rsp+30h+UserData], rdi; UserData
0x140005206  call    cs:__imp_EtwWrite
0x14000520d  nop     dword ptr [rax+rax+00h]
0x140005212  mov     rcx, rdi; ListEntry
0x140005215  mov     ebx, eax
0x140005217  call    SecReleaseEtwDescriptorBuffer
0x14000521c  mov     eax, ebx
0x14000521e  add     rsp, 30h
0x140005222  pop     r15
0x140005224  pop     r14
0x140005226  pop     r12
0x140005228  pop     rdi
0x140005229  pop     rsi
0x14000522a  pop     rbx
0x14000522b  pop     rbp
0x14000522c  retn
```
