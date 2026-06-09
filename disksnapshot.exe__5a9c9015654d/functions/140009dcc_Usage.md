# Usage

- ea: `0x140009dcc`
- end: `0x140009eda`
- name: `Usage`
- size: `270`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009ee0`

## callees

- `0x14000265e`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009de8`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009dff`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e16`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e2d`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e44`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e5b`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e72`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e89`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009ea0`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009eb7`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009de8`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009dff`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e16`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e2d`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e44`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e5b`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e72`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009e89`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009ea0`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009eb7`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x140009ed3`

## string_xrefs

- `0x140009df8`: `	-c write detail data to console\n`
- `0x140009e0f`: `	-i write detail data to console (same as -c)\n`
- `0x140009e54`: `	-j [config] specifies an alternate config file\n`
- `0x140009e6b`: `	-v [volume][path] specifies volume(+path) to process, e.g. "d:" or "d:\foo" \n`
- `0x140009ec7`: `	-o [output-file] write detail data to a file\n`

## pseudocode

```c
__int64 Usage()
{
  FILE *v0; // rax
  FILE *v1; // rax
  FILE *v2; // rax
  FILE *v3; // rax
  FILE *v4; // rax
  FILE *v5; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax

  v0 = o___acrt_iob_func_0(2u);
  _o_fputws(L"DiskSnapshot.exe [options]\n", v0);
  v1 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-c write detail data to console\n", v1);
  v2 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-i write detail data to console (same as -c)\n", v2);
  v3 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-s (deprecated) summary data to console\n", v3);
  v4 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-u process large volumes (no limit)\n", v4);
  v5 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-j [config] specifies an alternate config file\n", v5);
  v6 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-v [volume][path] specifies volume(+path) to process, e.g. \"d:\" or \"d:\\foo\" \n", v6);
  v7 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-d [input-file] print encoded versions of the strings in the input file, for decoding purposes\n", v7);
  v8 = o___acrt_iob_func_0(2u);
  _o_fputws(L"\t-e prints out escalation keywords\n", v8);
  v9 = o___acrt_iob_func_0(2u);
  _o_fputws(
    L"\t-k calculate checksums for files, used to investigate duplicated on-disk content (c arg required).\n",
    v9);
  v10 = o___acrt_iob_func_0(2u);
  return _o_fputws(L"\t-o [output-file] write detail data to a file\n", v10);
}

```

## disassembly

```asm
0x140009dcc  push    rbx
0x140009dce  sub     rsp, 20h
0x140009dd2  mov     ebx, 2
0x140009dd7  mov     ecx, ebx; Ix
0x140009dd9  call    _o___acrt_iob_func_0
0x140009dde  mov     rdx, rax
0x140009de1  lea     rcx, aDisksnapshotEx; "DiskSnapshot.exe [options]\n"
0x140009de8  call    cs:__imp__o_fputws
0x140009dee  mov     ecx, ebx; Ix
0x140009df0  call    _o___acrt_iob_func_0
0x140009df5  mov     rdx, rax
0x140009df8  lea     rcx, aCWriteDetailDa; "\t-c write detail data to console\n"
0x140009dff  call    cs:__imp__o_fputws
0x140009e05  mov     ecx, ebx; Ix
0x140009e07  call    _o___acrt_iob_func_0
0x140009e0c  mov     rdx, rax
0x140009e0f  lea     rcx, aIWriteDetailDa; "\t-i write detail data to console (same"...
0x140009e16  call    cs:__imp__o_fputws
0x140009e1c  mov     ecx, ebx; Ix
0x140009e1e  call    _o___acrt_iob_func_0
0x140009e23  mov     rdx, rax
0x140009e26  lea     rcx, aSDeprecatedSum; "\t-s (deprecated) summary data to conso"...
0x140009e2d  call    cs:__imp__o_fputws
0x140009e33  mov     ecx, ebx; Ix
0x140009e35  call    _o___acrt_iob_func_0
0x140009e3a  mov     rdx, rax
0x140009e3d  lea     rcx, aUProcessLargeV; "\t-u process large volumes (no limit)\n"
0x140009e44  call    cs:__imp__o_fputws
0x140009e4a  mov     ecx, ebx; Ix
0x140009e4c  call    _o___acrt_iob_func_0
0x140009e51  mov     rdx, rax
0x140009e54  lea     rcx, aJConfigSpecifi; "\t-j [config] specifies an alternate co"...
0x140009e5b  call    cs:__imp__o_fputws
0x140009e61  mov     ecx, ebx; Ix
0x140009e63  call    _o___acrt_iob_func_0
0x140009e68  mov     rdx, rax
0x140009e6b  lea     rcx, aVVolumePathSpe; "\t-v [volume][path] specifies volume(+p"...
0x140009e72  call    cs:__imp__o_fputws
0x140009e78  mov     ecx, ebx; Ix
0x140009e7a  call    _o___acrt_iob_func_0
0x140009e7f  mov     rdx, rax
0x140009e82  lea     rcx, aDInputFilePrin; "\t-d [input-file] print encoded version"...
0x140009e89  call    cs:__imp__o_fputws
0x140009e8f  mov     ecx, ebx; Ix
0x140009e91  call    _o___acrt_iob_func_0
0x140009e96  mov     rdx, rax
0x140009e99  lea     rcx, aEPrintsOutEsca; "\t-e prints out escalation keywords\n"
0x140009ea0  call    cs:__imp__o_fputws
0x140009ea6  mov     ecx, ebx; Ix
0x140009ea8  call    _o___acrt_iob_func_0
0x140009ead  mov     rdx, rax
0x140009eb0  lea     rcx, aKCalculateChec; "\t-k calculate checksums for files, use"...
0x140009eb7  call    cs:__imp__o_fputws
0x140009ebd  mov     ecx, ebx; Ix
0x140009ebf  call    _o___acrt_iob_func_0
0x140009ec4  mov     rdx, rax
0x140009ec7  lea     rcx, aOOutputFileWri; "\t-o [output-file] write detail data to"...
0x140009ece  add     rsp, 20h
0x140009ed2  pop     rbx
0x140009ed3  jmp     cs:__imp__o_fputws
```
