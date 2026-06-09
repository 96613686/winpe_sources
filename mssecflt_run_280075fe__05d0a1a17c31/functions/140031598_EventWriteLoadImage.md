# EventWriteLoadImage

- ea: `0x140031598`
- end: `0x140031924`
- name: `EventWriteLoadImage`
- size: `908`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, __int64, __int64, __int64, char, char, char, char, char, char, char, __int64, __int64, wchar_t *, char, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003205c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140011650`
- `0x140031598`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400318ee`
- `ntoskrnl!EtwWrite` at `0x1400318ee`
- `ntoskrnl!RtlLengthSid` at `0x140031639`
- `ntoskrnl!RtlLengthSid` at `0x140031639`

## pseudocode

```c
__int64 __fastcall EventWriteLoadImage(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        wchar_t *Str,
        char a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16,
        char a17,
        char a18,
        __int64 a19,
        __int64 a20,
        wchar_t *a21,
        char a22,
        __int64 a23)
{
  PSID v23; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v27; // eax
  const wchar_t *v28; // rsi
  int v29; // ebx
  int v30; // ecx
  __int64 v31; // rcx
  const WCHAR *v32; // r14
  const WCHAR *v33; // rax
  const wchar_t *v34; // rsi
  bool v35; // zf
  int v36; // eax
  __int64 v37; // rax
  int *v38; // rcx
  int *v39; // rdx
  int *v40; // rax
  unsigned int v41; // ebx
  int v42; // [rsp+30h] [rbp-18h] BYREF
  __int64 v43; // [rsp+90h] [rbp+48h] BYREF
  int v44; // [rsp+98h] [rbp+50h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+58h] BYREF
  int v46; // [rsp+A8h] [rbp+60h] BYREF

  v46 = a4;
  v45 = a3;
  v44 = a2;
  v43 = a1;
  v23 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(28);
  UserData = EtwDescriptorBuffer;
  v42 = 0;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v43;
  EtwDescriptorBuffer[2] = &v44;
  EtwDescriptorBuffer[4] = &v45;
  EtwDescriptorBuffer[6] = &v46;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v23 )
    v27 = RtlLengthSid(v23);
  else
    v27 = 0;
  v28 = Str;
  *((_DWORD *)UserData + 18) = v27;
  UserData[8] = v23;
  v29 = 2;
  UserData[10] = &a6;
  *((_DWORD *)UserData + 19) = 0;
  UserData[11] = 4;
  if ( v28 )
    v30 = 2 * wcslen_0(v28) + 2;
  else
    v30 = 2;
  *((_DWORD *)UserData + 26) = v30;
  v31 = a20;
  v32 = &SourceString;
  v33 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  if ( v28 )
    v33 = v28;
  UserData[15] = 4;
  v34 = a21;
  UserData[12] = v33;
  UserData[14] = &a8;
  UserData[16] = a9;
  UserData[18] = a10;
  UserData[20] = a11;
  UserData[22] = &a12;
  UserData[24] = &a13;
  UserData[26] = &a14;
  UserData[28] = &a15;
  UserData[30] = &a16;
  UserData[32] = &a17;
  UserData[34] = &a18;
  UserData[36] = a19;
  UserData[38] = v31 + 4;
  UserData[40] = v31 + 8;
  UserData[42] = v31 + 12;
  UserData[44] = v31 + 16;
  UserData[17] = 32;
  UserData[19] = 20;
  UserData[21] = 16;
  UserData[23] = 4;
  UserData[25] = 4;
  UserData[27] = 4;
  UserData[29] = 4;
  UserData[31] = 8;
  UserData[33] = 8;
  UserData[35] = 8;
  UserData[37] = 64;
  UserData[39] = 4;
  UserData[41] = 4;
  UserData[43] = 4;
  UserData[45] = 1;
  v35 = v34 == 0;
  if ( v34 )
  {
    v36 = wcslen_0(v34);
    v35 = v34 == 0;
    v29 = 2 * v36 + 2;
  }
  *((_DWORD *)UserData + 94) = v29;
  if ( !v35 )
    v32 = v34;
  UserData[48] = &a22;
  v37 = a23;
  UserData[46] = v32;
  *((_DWORD *)UserData + 95) = 0;
  UserData[49] = 4;
  if ( v37 )
  {
    v38 = (int *)(v37 + 48);
    v39 = (int *)(v37 + 52);
    v40 = (int *)(v37 + 72);
  }
  else
  {
    v38 = &v42;
    v39 = &v42;
    v40 = &v42;
  }
  UserData[50] = v40;
  UserData[51] = 4;
  UserData[52] = v39;
  UserData[53] = 4;
  UserData[54] = v38;
  UserData[55] = 4;
  v41 = EtwWrite(Microsoft_Windows_SECHandle, &Event23, 0, 0x1Cu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v41;
}

```

## disassembly

```asm
0x140031598  mov     rax, rsp
0x14003159b  mov     [rax+20h], r9d
0x14003159f  mov     [rax+18h], r8
0x1400315a3  mov     [rax+10h], edx
0x1400315a6  mov     [rax+8], rcx
0x1400315aa  push    rbp
0x1400315ab  push    rbx
0x1400315ac  push    rsi
0x1400315ad  push    rdi
0x1400315ae  push    r12
0x1400315b0  push    r13
0x1400315b2  push    r14
0x1400315b4  push    r15
0x1400315b6  mov     rbp, rsp
0x1400315b9  sub     rsp, 48h
0x1400315bd  mov     rax, cs:__security_cookie
0x1400315c4  xor     rax, rsp
0x1400315c7  mov     [rbp+var_10], rax
0x1400315cb  mov     rbx, [rbp+Sid]
0x1400315cf  mov     ecx, 1Ch
0x1400315d4  call    SecGetEtwDescriptorBuffer
0x1400315d9  xor     r15d, r15d
0x1400315dc  mov     rdi, rax
0x1400315df  mov     [rbp+var_18], r15d
0x1400315e3  test    rax, rax
0x1400315e6  jnz     short loc_1400315F2
0x1400315e8  mov     eax, 0C000009Ah
0x1400315ed  jmp     loc_140031906
0x1400315f2  mov     qword ptr [rdi+8], 8
0x1400315fa  lea     rax, [rbp+arg_0]
0x1400315fe  mov     [rdi], rax
0x140031601  lea     rax, [rbp+arg_8]
0x140031605  mov     [rdi+10h], rax
0x140031609  lea     rax, [rbp+arg_10]
0x14003160d  mov     [rdi+20h], rax
0x140031611  lea     rax, [rbp+arg_18]
0x140031615  mov     [rdi+30h], rax
0x140031619  mov     qword ptr [rdi+18h], 4
0x140031621  mov     qword ptr [rdi+28h], 8
0x140031629  mov     qword ptr [rdi+38h], 4
0x140031631  test    rbx, rbx
0x140031634  jz      short loc_140031647
0x140031636  mov     rcx, rbx; Sid
0x140031639  call    cs:__imp_RtlLengthSid
0x140031640  nop     dword ptr [rax+rax+00h]
0x140031645  jmp     short loc_14003164A
0x140031647  mov     eax, r15d
0x14003164a  mov     rsi, [rbp+Str]
0x14003164e  mov     [rdi+48h], eax
0x140031651  lea     rax, [rbp+arg_28]
0x140031655  mov     [rdi+40h], rbx
0x140031659  mov     ebx, 2
0x14003165e  mov     [rdi+50h], rax
0x140031662  mov     [rdi+4Ch], r15d
0x140031666  mov     qword ptr [rdi+58h], 4
0x14003166e  test    rsi, rsi
0x140031671  jz      short loc_140031684
0x140031673  mov     rcx, rsi; Str
0x140031676  call    wcslen_0
0x14003167b  lea     ecx, ds:2[rax*2]
0x140031682  jmp     short loc_140031686
0x140031684  mov     ecx, ebx
0x140031686  test    rsi, rsi
0x140031689  mov     [rdi+68h], ecx
0x14003168c  mov     rcx, [rbp+arg_98]
0x140031693  lea     r14, SourceString
0x14003169a  mov     rax, r14
0x14003169d  mov     [rdi+6Ch], r15d
0x1400316a1  cmovnz  rax, rsi
0x1400316a5  mov     qword ptr [rdi+78h], 4
0x1400316ad  mov     rsi, [rbp+arg_A0]
0x1400316b4  mov     [rdi+60h], rax
0x1400316b8  lea     rax, [rbp+arg_38]
0x1400316bf  mov     [rdi+70h], rax
0x1400316c3  mov     rax, [rbp+arg_40]
0x1400316ca  mov     [rdi+80h], rax
0x1400316d1  mov     rax, [rbp+arg_48]
0x1400316d8  mov     [rdi+90h], rax
0x1400316df  mov     rax, [rbp+arg_50]
0x1400316e6  mov     [rdi+0A0h], rax
0x1400316ed  lea     rax, [rbp+arg_58]
0x1400316f4  mov     [rdi+0B0h], rax
0x1400316fb  lea     rax, [rbp+arg_60]
0x140031702  mov     [rdi+0C0h], rax
0x140031709  lea     rax, [rbp+arg_68]
0x140031710  mov     [rdi+0D0h], rax
0x140031717  lea     rax, [rbp+arg_70]
0x14003171e  mov     [rdi+0E0h], rax
0x140031725  lea     rax, [rbp+arg_78]
0x14003172c  mov     [rdi+0F0h], rax
0x140031733  lea     rax, [rbp+arg_80]
0x14003173a  mov     [rdi+100h], rax
0x140031741  lea     rax, [rbp+arg_88]
0x140031748  mov     [rdi+110h], rax
0x14003174f  mov     rax, [rbp+arg_90]
0x140031756  mov     [rdi+120h], rax
0x14003175d  lea     rax, [rcx+4]
0x140031761  mov     [rdi+130h], rax
0x140031768  lea     rax, [rcx+8]
0x14003176c  mov     [rdi+140h], rax
0x140031773  lea     rax, [rcx+0Ch]
0x140031777  mov     [rdi+150h], rax
0x14003177e  lea     rax, [rcx+10h]
0x140031782  mov     [rdi+160h], rax
0x140031789  mov     qword ptr [rdi+88h], 20h ; ' '
0x140031794  mov     qword ptr [rdi+98h], 14h
0x14003179f  mov     qword ptr [rdi+0A8h], 10h
0x1400317aa  mov     qword ptr [rdi+0B8h], 4
0x1400317b5  mov     qword ptr [rdi+0C8h], 4
0x1400317c0  mov     qword ptr [rdi+0D8h], 4
0x1400317cb  mov     qword ptr [rdi+0E8h], 4
0x1400317d6  mov     qword ptr [rdi+0F8h], 8
0x1400317e1  mov     qword ptr [rdi+108h], 8
0x1400317ec  mov     qword ptr [rdi+118h], 8
0x1400317f7  mov     qword ptr [rdi+128h], 40h ; '@'
0x140031802  mov     qword ptr [rdi+138h], 4
0x14003180d  mov     qword ptr [rdi+148h], 4
0x140031818  mov     qword ptr [rdi+158h], 4
0x140031823  mov     qword ptr [rdi+168h], 1
0x14003182e  test    rsi, rsi
0x140031831  jz      short loc_140031845
0x140031833  mov     rcx, rsi; Str
0x140031836  call    wcslen_0
0x14003183b  test    rsi, rsi
0x14003183e  lea     ebx, ds:2[rax*2]
0x140031845  lea     rax, [rbp+arg_A8]
0x14003184c  mov     [rdi+178h], ebx
0x140031852  cmovnz  r14, rsi
0x140031856  mov     [rdi+180h], rax
0x14003185d  mov     rax, [rbp+arg_B0]
0x140031864  mov     [rdi+170h], r14
0x14003186b  mov     [rdi+17Ch], r15d
0x140031872  mov     qword ptr [rdi+188h], 4
0x14003187d  test    rax, rax
0x140031880  jz      short loc_140031890
0x140031882  lea     rcx, [rax+30h]
0x140031886  lea     rdx, [rax+34h]
0x14003188a  add     rax, 48h ; 'H'
0x14003188e  jmp     short loc_14003189C
0x140031890  lea     rcx, [rbp+var_18]
0x140031894  lea     rdx, [rbp+var_18]
0x140031898  lea     rax, [rbp+var_18]
0x14003189c  mov     [rdi+190h], rax
0x1400318a3  mov     r9d, 1Ch; UserDataCount
0x1400318a9  mov     qword ptr [rdi+198h], 4
0x1400318b4  xor     r8d, r8d; ActivityId
0x1400318b7  mov     [rdi+1A0h], rdx
0x1400318be  lea     rdx, Event23; EventDescriptor
0x1400318c5  mov     qword ptr [rdi+1A8h], 4
0x1400318d0  mov     [rdi+1B0h], rcx
0x1400318d7  mov     qword ptr [rdi+1B8h], 4
0x1400318e2  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400318e9  mov     [rsp+48h+UserData], rdi; UserData
0x1400318ee  call    cs:__imp_EtwWrite
0x1400318f5  nop     dword ptr [rax+rax+00h]
0x1400318fa  mov     rcx, rdi; ListEntry
0x1400318fd  mov     ebx, eax
0x1400318ff  call    SecReleaseEtwDescriptorBuffer
0x140031904  mov     eax, ebx
0x140031906  mov     rcx, [rbp+var_10]
0x14003190a  xor     rcx, rsp; StackCookie
0x14003190d  call    __security_check_cookie
0x140031912  add     rsp, 48h
0x140031916  pop     r15
0x140031918  pop     r14
0x14003191a  pop     r13
0x14003191c  pop     r12
0x14003191e  pop     rdi
0x14003191f  pop     rsi
0x140031920  pop     rbx
0x140031921  pop     rbp
0x140031922  retn
```
